# CharacterAlignerScaler

CharacterAlignerScaler 是一個用於對齊和縮放字符圖像的工具。它允許您根據指定的比例和最小尺寸來處理字符圖像，並將結果保存到指定的輸出文件夾。此外，本專案還包含一個用於顯示對齊和縮放操作前後的字符圖像的程式碼片段。

## 功能

- 對齊字符圖像：根據字符的邊界框將字符放在新圖像的中心
- 縮放字符圖像：根據指定的縮放百分比來縮放字符(非中文字跳過，不處理)
- 顯示操作前後的字符圖像對比

## 安裝

1. clone這個專案：
```
git clone https://github.com/TaylorNTUT/CharacterAlignerScaler.git
```

2. 切換到專案目錄：
```
cd CharacterAlignerScaler
```

3. 創建並激活虛擬環境（可選）：
```
python -m venv venv
source venv/bin/activate # 在 Windows 上使用 venv\Scripts\activate
```

4. 安裝所需的依賴項：
```
pip install -r requirements.txt
```


## 使用方法

### align_and_scale_chr.py

* 把要處理的資料夾放到CharacterAlignerScaler這個資料夾下

執行以下命令來使用 CharacterAlignerScaler：
```
python align_and_scale_chr.py -f INPUT_FOLDER -o OUTPUT_FOLDER [-S] [-s SCALE_PERCENTAGE] [-m MIN_SIZE] [-A]
```
- `-f`, `--input-folder`: 包含 .png 文件的輸入文件夾
- `-o`, `--output-folder`: 處理後圖像的輸出文件夾(如果沒有會建一個)
- `-S`, `--scale`: 執行縮放操作
- `-s`, `--scale-percentage`: 縮放操作的縮放百分比（默認值：95）
- `-m`, `--min-size`: 最小邊界框尺寸，也就是如果opencv抓到低於這個尺寸的邊框，不處理（默認值：50）
- `-A`, `--align`: 執行對齊操作


### compare.py (用來顯示操作前後的字符圖像對比)

使用下面的程式碼片段來顯示對齊和縮放操作前後的字符圖像對比：

注意：在運行顯示操作前後的字符圖像對比的程式碼片段之前，請確保已將 `before_folder` 和 `after_folder` 變量替換為實際的輸入和輸出文件夾名稱。

```python
before_folder = "./1_138"  # 請將 "./1_138" 替換換成實際的輸入文件夾名稱
after_folder = "1_138_after" # 請將 "1_138_after" 替換成實際的輸出文件夾名稱
display_images(before_folder, after_folder, 10) # 最後一個參數表示要展示的圖像對的數量
```


## 示例

要對 `1_138` 文件夾中的圖像進行對齊和縮放，並將結果保存到 `1_138_after` 文件夾，您可以使用以下命令：
```
python align_and_scale_chr.py -f 1_138 -o 1_138_after -S -A
```

要對 `1_138` 文件夾中的圖像進行對齊和「縮放操作的縮放百分比：90」和「最小邊界框尺寸：60」，並將結果保存到 `1_138_after` 文件夾，您可以使用以下命令：
```
python align_and_scale_chr.py -f 1_138 -o 1_138_after -S -A -s 90 -m 60
```

要對 `1_138` 和 `1_138_after` 裡面的圖像隨機抽取10個做比較，並輸出比較的圖：
```
python compare.py
```








