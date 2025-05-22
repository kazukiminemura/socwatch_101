# Windows上でのSoCWatch 
## ステップ１
SoCWatchのインストールと設定
Intel VTuneをインストールするとSoCWatchもインストールされます。
```
set PATH="C:\Program Files (x86)\Intel\oneAPI\vtune\latest\socwatch\64";%PATH%
```

## ステップ２
Intel® SoC Watch がインストールされた対象システムで、管理者権限でコマンドプロンプトを開きます。  
以下のコマンドを実行して、60 秒間にわたる低電力状態での CPU 時間をキャプチャし、その結果を Intel® VTune™ Profiler にインポートします。  

```
socwatch -t 60 -f cpu-cstate -m -o results/test -r vtune
```
レポートファイルは、results ディレクトリに test.pwr という名前で保存されます。

結果例
```
--------------------------------------------------------------------------
Intel(R) SoC Watch for Windows* OS Version 2025.0.0 [Jan 24 2025]
Build Ref: dde74fec6522911903699289a9e25392b33a86c0
Driver Version 2.20.1 [Oct  1 2024]
Copyright (c) 2024 Intel Corporation. All Rights Reserved.
Platform power analysis tool for use with Intel processors/chipsets/platforms.
*Other names and brands may be claimed as the property of others.
--------------------------------------------------------------------------

Platform specification: CPU=0x6.0x8c.0x1 PCH=0xa082
NOTE: Hyper-V is enabled on this system.
NOTE: Virtual Secure Mode is enabled on this system.

*** Started 60 seconds data collection. Use Ctrl-C to stop collection.
*** Post-processing results.
 Processing ETW data for Info (metadata) Session.
 Processing ETW data for Extra data Session.
 Processing ETW data for HW data Session.
 Processing ETW data for OS data Session.
FATAL: Warning: Lost events detected (5975159) in results\test_osSession.etl.
*** Data written to: C:\Users\kminemur\source\socwatch_101\results\test
```

## ステップ3
