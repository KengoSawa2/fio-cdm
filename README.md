# fio-cdm
fioでCrystalDiskMarkっぽい計測を行うコマンド
fio 2.xがインストールされている環境で使えるよ

## Usage

```
aio2.xの場合
fio-cdm <path> <testsize>
```
```
aio3.xの場合
TARGET=テストディスクパス fio -f fio3.txt --output-format=terse | awk -F ';' '{print $3, ($7+$48) / 1000}'
テストサイズはfio3.txtの中身を適宜書き換えてね
```

### sample

```
# fio-cdm /mnt/hogepoint 8g
|      | Read(MB/s)|Write(MB/s)|
|------|-----------|-----------|
|  Seq |    305.307|    138.191|
| 512K |    275.565|    139.452|
|   4K |     22.208|     37.098|
|4KQD32|    210.052|    125.907|
```

## 参考
* [LinuxのI/OベンチマークでCrystalDiskMarkと同等の計測をfioで実現 - WinKey](http://www.winkey.jp/article.php/20110310142828679)
