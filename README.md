# CharacterAlignerScaler

CharacterAlignerScaler 是一個用於對齊和縮放字符圖像的工具。它允許您根據指定的比例和最小尺寸來處理字符圖像，並將結果保存到指定的輸出文件夾。

## 功能

- 對齊字符圖像：根據字符的邊界框將字符放在新圖像的中心
- 縮放字符圖像：根據指定的縮放百分比來縮放字符

## 安裝

1. 克隆這個專案：
```git clone https://github.com/TaylorNTUT/CharacterAlignerScaler.git```

2. 切換到專案目錄：
```cd CharacterAlignerScaler```

3. 創建並激活虛擬環境（可選）：
```python -m venv venv
source venv/bin/activate # 在 Windows 上使用 venv\Scripts\activate```

4. 安裝所需的依賴項：
```pip install -r requirements.txt```


## 使用方法

執行以下命令來使用 CharacterAlignerScaler：
python align_and_scale_chr.py -f INPUT_FOLDER -o OUTPUT_FOLDER [-S] [-s SCALE_PERCENTAGE] [-m MIN_SIZE] [-A]

- `-f`, `--input-folder`: 包含 .png 文件的輸入文件夾
- `-o`, `--output-folder`: 處理後圖像的輸出文件夾
- `-S`, `--scale`: 執行縮放操作
- `-s`, `--scale-percentage`: 縮放操作的縮放百分比（默認值：95）
- `-m`, `--min-size`: 最小邊界框尺寸（默認值：50）
- `-A`, `--align`: 執行對齊操作

## 示例

要對 `input_images` 文件夾中的圖像進行對齊和縮放，並將結果保存到 `output_images` 文件夾，您可以使用以下命令：
python align_and_scale_chr.py -f input_images -o output_images -S -A






