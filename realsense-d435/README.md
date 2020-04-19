How to use
====

## 事前準備

directory 構造は下記
```
home/work/realsense/
```

移動
```
$ cd ~/MyDockerfiles/realsense-d435
```

コンテナのビルド

```
$ docker build --tag=realsense .
```

※以後、必ずDockerはrealsensディレクトリ内でRUN
 
 
 移動
```
$ cd ~/work/realsense/
```
 ※以後、必ずDockerはrealsenseでRUN


 ## X window のエラーを回避する
 
.bashrcを開く
```
$ vim ~/.bashrc
```

環境変数QT_X11_NO_MITSHM=1を追記
```
export QT_X11_NO_MITSHM=1
```

環境変数の追加を反映
```
$ source ~/.bashrc
```

環境変数が正しく追加されているか確認
```
$ echo $QT_X11_NO_MITSHM
```
※1と出ればOK

 詳細は右記リンク先を参照
 ([参考1](https://qiita.com/oreyutarover/items/cca3511012b6ad97a1ce))
 ([参考2](https://qiita.com/tnarihi/items/275c009e9dec1306893f))


## Run

ディスプレイへの接続を許可
```
$ xhost +
```

起動
```
$ docker run -it --rm --privileged --gpus all --net host -e DISPLAY=$DISPLAY --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" -v $(pwd):/realsense/ realsense
```


[genmai99](https://github.com/genmai99)