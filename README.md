# Gaze Input Shooting Game

カメラから取得した顔・目のランドマークを利用し、視線とまばたきで魚をすくうゲームです。

## 動作確認環境

- Windows 11
- Python 3.12.10
- OpenCV (`opencv-contrib-python`) 4.11.0.86
- MediaPipe 0.10.21
- NumPy 1.26.4
- Pygame 2.6.1

上記は開発時に動作確認したバージョンです。

## 必要なライブラリのインストール

プロジェクトのルートディレクトリで、次のコマンドを実行します。

```powershell
python -m pip install --upgrade pip
python -m pip install opencv-contrib-python==4.11.0.86 mediapipe==0.10.21 numpy==1.26.4 pygame==2.6.1
```

PygameはBGMと効果音の再生に使用します。音声をすべて無効にして実行する場合は、Pygameを使用しません。

## 起動方法

カメラ番号が `1` の場合は、次のコマンドで起動します。

```powershell
python .\scripts\gaze_shooting_game.py --camera 1
```

カメラが認識されない場合は、`--camera` の番号を `0`、`1`、`2` などに変更してください。

## 省電力モード

内部では1280×720で描画し、表示時に1920×1080へ拡大します。通常の1920×1080内部描画より、CPU負荷と消費電力を抑えられます。

```powershell
python .\scripts\gaze_shooting_game.py --camera 1 --internal-render-720p
```

## 音声を無効にする場合

```powershell
python .\scripts\gaze_shooting_game.py --camera 1 --no-bgm --no-catch-se --no-break-se --no-clear-se
```

省電力モードと同時に指定することもできます。

```powershell
python .\scripts\gaze_shooting_game.py --camera 1 --internal-render-720p --no-bgm --no-catch-se --no-break-se --no-clear-se
```

## インストール済みバージョンの確認

```powershell
python --version
python -m pip show opencv-contrib-python mediapipe numpy pygame
```
