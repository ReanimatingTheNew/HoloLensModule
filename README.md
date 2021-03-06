# HoloLensModule
- Windows10 Creators Update
- Unity 5.6.1,Unity 2017.1.2, Unity 2017.2.0
- Visual Studio 2015,2017
----------
## 概要
HoloLensでハンドジェスチャー及び各種機能を利用するためのツールキットです．
ハンドジェスチャー，ネットワーク，ユーティリティで必要な機能を追加していきます．


youtube : [HoloLensModule](https://youtu.be/VPHf6SsW9BA)

## 内容
### Input : ハンドジェスチャーに関するモジュール
        * 認識できるハンドジェスチャーは以下
            - 片手ジェスチャー
            - Tap
            - DoubleTap
            - Hold
            - Drag
            - 両手を出して片手だけジェスチャー
            - ShiftTap
            - ShiftDoubleTap
            - ShiftHold
            - ShiftDrag
            - 両手でジェスチャー
            - MultiTap
            - MultiDoubleTap
            - MultiDrag
- Prefabs
    + HandObject.prefab
        * InputModule.prefab内で利用する認識した手に追従するオブジェクト
    + InputModule.prefab
        * Scene内に一つは位置することで手のトラッキングとジェスチャーの認識を行う
- Scripts
    + DragGestureEvent.cs
        * Drag(Shift,Multi Drag)動作を受け取りイベントを呼び出す
    + HandGestureLog.cs
        * 認識したジェスチャーをConsoleに表示する
    + HandObjectControl.cs
        * トラッキングした手の位置とPress状態を表示
    + HandsGestureManager.cs
        * ジェスチャーの認識
    + HandsInteractionManager.cs
        * 手のトラッキング
    + ObjectMoveControl.cs
        * オブジェクトの移動(Colliderがついているオブジェクトにアタッチ)
    + ObjectRotationControl.cs
        * オブジェクトの回転(Colliderがついているオブジェクトにアタッチ)
    + ObjectScaleControl.cs
        * オブジェクトのサイズ(Colliderがついているオブジェクトにアタッチ)
    + RayCastControl.cs
        * 視線上のオブジェクトを検出する
    + TapGestureEvent.cs
        * Tap(Double Tap, Hold, Shift, Multi)動作を受け取りイベントを呼び出す
### Network : TCP,UDP,RestAPIでの通信を行うためのモジュール
- RestAPI/Scripts
    + RestAPIJsonManager.cs
        * RestAPIのGETとPOSTを行う
- TCP/Scripts
    + TcpNetworkClientManager.cs
        * Tcpネットワークのクライアント制御
    + TcpNetworkServerManager.cs
        * Tcpネットワークのサーバー制御(HoloLens側は未実装)
- UDP/Scripts
    + UdpNetworkClientManager.cs
        * Udpネットワークの送信制御
    + UdpNetworkListenManager.cs
        * Udpネットワークの受信制御
### Secenes : ハンドジェスチャーを確認するためのサンプルScene
- sample.unity
### Utilities
- Scripts
    + BaseSceneFunction.cs
        * シーン変更時に指定のオブジェクトを削除しないようにする
    + BodyLockObject.cs
        * オブジェクトをBodylock(常に視線の先に遅れて追従する)の状態にする
    + Boundingbox.cs
        * MeshFilterのあるGameObjectに対してフレームとBoxColliderを付与
    + DebugConsole.cs
        * コンソール出力を取得してUIのTextに渡す
    + DeviceActiveControl.cs
        * 特定のデバイス(HoloLens or Desktop)のみでオブジェクトを有効にさせる
    + HoloLensModuleSingleton.cs
        * シングルトン
    + SkyboxControl.cs
        * HoloLensとImmersiveとEditorの背景を分ける(Unity 2017.2から有効)
    + WorldAnchorControl.cs
        * ワールドアンカー制御

## 今後の予定
- Unity2017.2の対応
- Windows Immersive HMDの対応+モーションコントローラーの対応
