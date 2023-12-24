import os
import random
from PIL import Image
import matplotlib.pyplot as plt

class ImageVisualizer:
    def __init__(self, dir, N):
        self.folder_path = dir
        self.N = N

    def _get_image_files(self):
        return [f for f in os.listdir(self.folder_path) if f.lower().endswith(('.png', '.jpg', '.jpeg', '.gif', '.bmp'))]

    def visualize_images(self):
        # 폴더 내의 이미지 파일 목록 가져오기
        image_files = self._get_image_files()

        # 랜덤으로 9개 이미지 선택
        selected_images = random.sample(image_files, self.N*self.N)

        # 3x3 그리드로 시각화
        fig, axs = plt.subplots(self.N, self.N, figsize=(10, 10))

        for i, ax in enumerate(axs.flat):
            img_name = selected_images[i]
            img_path = os.path.join(self.folder_path, img_name)

            # 이미지 불러오기
            img = Image.open(img_path)

            # 이미지 표시
            ax.imshow(img)
            ax.axis('off')

            # 이미지 이름과 가로세로 길이 출력
            img_width, img_height = img.size
            ax.set_title(f"{img_name}\nWidth: {img_width}, Height: {img_height}")

        # 그리드 간격 조정
        plt.tight_layout()

        # 시각화 결과 보여주기
        plt.show()
