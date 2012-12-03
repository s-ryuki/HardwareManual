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

　　　　　サーボモータ：PRS-FF09PⅡ（Pirkus製）  
　　　　　電源：LiPo 7.4V (Hyperion製)  
　　　　　使用マイコン：mbed NXP LPC1768  
　  
### 2．コマンド方式のサーボモータを用いたロボット ###
　　　[![画像2][image2]](http://cloud.github.com/downloads/s-ryuki/Pictures/3axis_prs-s40m2.png)
[image2]:http://cloud.github.com/downloads/s-ryuki/Pictures/3axis_prs-s40m2.png

　　　　　サーボモータ：PRS-S40M（Pirkus製）  
　　　　　電源：LiPo 7.4V  (Hyperion製)  

　　　　　PRS-S40Mのハードウェアマニュアルはこちらをご覧ください。  
　  
　　　　　　　[PRS-DE07MS/PRS-S40M ハードウェアマニュアル](http://cloud.github.com/downloads/s-ryuki/HardwareManual/PRS-DE07MS_PRS-S40M_%E7%AC%AC%E5%9B%9B%E7%89%88.pdf)
　  
　  
ロボットの製作
------------
　これらのロボットは市販されているサーボモータを使用し、  
フレームはホビーロボットを自主制作する際に通常行うようなアルミ板の切削加工、曲げ加工等を施して製作しました。
　  
#### (1)板金の切削加工 ####
　まずはアルミ板からフレームを削り出します。
　使用する部材はA5052のt1.5mmのアルミ板です。これは各ロボットショップで購入可能です。　  
　切削加工に用いるDXFデータをそれぞれのロボットに関してアップロードしましたのでご使用ください。  
　  
　　　　PRS-FF09PⅡ用：[3axis_prs-ff09pii_frame.dxf]()  
　　　　PRS-S40M用：[3axis_prs-s40m_frame.dxf]()  
　  
#### (2)各パーツの追加工 #####
　切削できたパーツはバリを取り除いた後、「ねじ切り加工」と「曲げ加工」を行います。
　以下の図は「3axis_prs-ff09pii_frame.dxf(1)・(2)」と同様に配置された図面です。
　まず以下の赤で囲まれている穴にM2の雌ねじを切ります。  
　ホームセンサー等で市販されているM2タップをご使用ください。ネジを切る際には切削油を用い、  
　切り粉が切り粉が詰まらないように注意してください。
　  
　次に曲げ加工を行います。以下の



[Robotma.com](http://www.robotma.com/)では「オリジナルロボット製作支援サービス」としてDXFデータを渡せば  
アルミ板の切削加工を代行するサービスがあります。ほかのロボットショップでもこのような  
加工代行サービスを行っているところは多く、加工設備が無い場合でも製作できますので、お試しください。  
　    
　このようなロボットは私たちの研究で使用した２種類のサーボモータ以外のものを用いても製作可能です。  
各軸間等を揃えたフレームを用いれば、入手しやすいサーボモータを使用してもロボットを動かすことができます。  
またフレームは、タミヤ社製ユニバーサルプレート（[http://www.tamiya.com/japan/products/70172plate/index.htm](http://www.tamiya.com/japan/products/70172plate/index.htm)）等を  
使用すれば簡単に製作できます。　　
