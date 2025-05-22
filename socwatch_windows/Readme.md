# Windows上でのSoCWatch 
## ステップ１
SoCWatchのインストールと設定
Intel VTuneをインストールするとSoCWatchもインストールされます。

## ステップ２
Intel® SoC Watch がインストールされた対象システムで、管理者権限でコマンドプロンプトを開きます。  
以下のコマンドを実行して、60 秒間にわたる低電力状態での CPU 時間をキャプチャし、その結果を Intel® VTune™ Profiler にインポートします。  

```
socwatch -t 60 -f cpu-cstate -m -o results/test -r vtune
```

