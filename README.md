ハードウェアの説明
==================
　ここでは本研究の実験に用いたロボットの説明をします。  

ロボット概要
------------
今回はヒューマノイドロボットの最も簡易的なモデルである、3軸のロボットを用いました。  
このロボットは左右の足にピッチ方向の軸を、胴体にロール方向の軸を持っており、  
胴体を左右に振りながら重心を移動し、足を交互に前に出すことで歩行することができます。  
　  
　私たちはサーボの種類によって2機のロボットを製作し、実験に用いました。
### 1．PWM方式のサーボモータを用いたロボット ###
　　　[![画像1][image1]](http://cloud.github.com/downloads/s-ryuki/Pictures/3axis_prs-ff09pii.png)
[image1]:http://cloud.github.com/downloads/s-ryuki/Pictures/3axis_prs-ff09pii.png

　　　　　サーボモータ：[PRS-FF09PⅡ](http://www.pirkus.co.jp/products_servo09.html)（Pirkus製）  
　　　　　電源：LiPo 7.4V 1100mAh (Hyperion製)  
　　　　　使用マイコン：mbed NXP LPC1768  
　  
　　　　また、このロボットには実験のため、センサを搭載しました。  
　　　[![画像2][image2]](http://cloud.github.com/downloads/s-ryuki/Pictures/sensor_picture.png)
[image2]:http://cloud.github.com/downloads/s-ryuki/Pictures/sensor_picture.png
　　　　　3軸加速度センサ [KXM52-1050](http://akizukidenshi.com/catalog/g/gI-01425/)　　（入手先：[秋月電子通商](http://akizukidenshi.com/catalog/default.aspx)）  
　　　　　　　　　電源電圧：2.7～5.5V  
　　　　　　　　　測定レンジ：±2G  
　　　　　　　　　感度：670mV/G（標準3.3V時）  
　　　　　　　　　　　
　  
### 2．コマンド方式のサーボモータを用いたロボット ###
　　　[![画像3][image3]](http://cloud.github.com/downloads/s-ryuki/Pictures/3axis_prs-s40m2.png)
[image3]:http://cloud.github.com/downloads/s-ryuki/Pictures/3axis_prs-s40m2.png

　　　　　サーボモータ：[PRS-S40M](http://www.pirkus.co.jp/products_servos04m.html)（Pirkus製）  
　　　　　電源：LiPo 7.4V  (Hyperion製)  

　　　　PRS-S40Mのマニュアルはこちらをご覧ください。  
　  
　　　　　　　[PRS-DE07MS/PRS-S40M マニュアル]
(http://cloud.github.com/downloads/s-ryuki/HardwareManual/PRS-DE07MS_PRS-S40M_%E7%AC%AC%E5%9B%9B%E7%89%88.pdf)（提供：株式会社ピルクス）
　  
　  
ロボットの製作
------------
　これらのロボットは市販されているサーボモータを使用し、  
フレームはホビーロボットを自主制作する際に通常行うようなアルミ板の切削加工、曲げ加工等を施して製作しました。
　  
#### (1)板金の切削加工 ####
　まずはアルミ板からフレームを削り出します。
　使用する部材はA5052のt1.5mmのアルミ板です。これは各ロボットショップで購入可能です。　  
　切削加工に用いるDXFデータをそれぞれのロボットに関してアップロードしましたのでご使用ください。  
　  
　　　　PRS-FF09PⅡ用：[3axis_prs-ff09pii_frame1.dxf](https://github.com/downloads/s-ryuki/HardwareManual/3axis_prs-ff09pii_frame1.dxf)  
　　　　　　　　　　　　[3axis_prs-ff09pii_frame2.dxf](https://github.com/downloads/s-ryuki/HardwareManual/3axis_prs-ff09pii_frame2.dxf)  
　　　　PRS-S40M用：[3axis_prs-s40m_frame1.dxf]()  
　　　　　　　　　　　　[3axis_prs-s40m_frame2.dxf]()  
　　　　　　　　　　　　[3axis_prs-s40m_frame3.dxf]()  
　  
#### (2)各パーツの追加工 ####
　切削できたパーツはバリを取り除いた後、「ねじ切り加工」と「曲げ加工」を行います。  
　以下の図は「3axis_prs-ff09pii_frame1.dxf、3axis_prs-ff09pii_frame2.dxf」と同様に配置された図面です。
　まず以下の赤で囲まれている穴にM2の雌ねじを切ります。  
　ホームセンサー等で市販されているM2タップをご使用ください。ネジを切る際には切削油を用い、  
　切り粉が詰まらないように注意してください。
　  
　次に曲げ加工を行います。以下の青いラインで各パーツを90度曲げます。  
　曲げ加工には板金専用のベンダーをお使いください。  
　  
　　[![画像4][image4]](http://cloud.github.com/downloads/s-ryuki/Pictures/3axis_prs-s40m2.png)
[image4]:http://cloud.github.com/downloads/s-ryuki/Pictures/3axis_prs-s40m2.png

　　[![画像5][image5]](http://cloud.github.com/downloads/s-ryuki/Pictures/3axis_prs-s40m2.png)
[image5]:http://cloud.github.com/downloads/s-ryuki/Pictures/3axis_prs-s40m2.png  
　  
　すべての加工が終了すると以下のようになります。
　なお、写真のパーツにはアルマイト処理が施されております。
　
　　[![画像6][image6]](http://cloud.github.com/downloads/s-ryuki/Pictures/Parts.png)
[image6]:http://cloud.github.com/downloads/s-ryuki/Pictures/Parts.png  
　  
#### (3)組立て ####
　これらのパーツを長さ5mm程度のM2ネジで組み上げます。  
　その後、頭の部分に重りを取り付け、足裏に体を左右に振るためのパーツを取り付けます。  
　最後に背中にコントロールボードを搭載し、各サーボを接続すれば完成です。
　  
　  
　  
なお、[Robotma.com](http://www.robotma.com/)では「オリジナルロボット製作支援サービス」としてDXFデータを渡せば  
アルミ板の切削加工を代行するサービスがあります。ほかのロボットショップでもこのような  
加工代行サービスを行っているところは多く、加工設備が無い場合でも製作できますので、お試しください。  
　    
　このようなロボットは私たちの研究で使用したサーボモータ以外のものを用いても製作可能です。  
各軸間等を揃えたフレームを用いれば、入手しやすいサーボモータを使用してもロボットを動かすことができます。  
　またアルミの加工が難しい場合は、フレームに[タミヤ社製ユニバーサルプレート](http://www.tamiya.com/japan/products/70172plate/index.htm)等を使用すれば簡単に製作できます。　　
