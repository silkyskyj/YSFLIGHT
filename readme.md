# YS Flight Simulator

by CaptainYS
http://www.ysflight.com

customized by silkysky  
https://github.com/silkyskyj/YSFLIGHT

 2025/09/14 Ver20250914  
 1. ズーム軸を追加 (テストバージョン、後ろ向いた時はうまく動作しません)  https://github.com/silkyskyj/YSFLIGHT/issues/6   
 2. ジョイスティックのZoom in とZoom Outでボタンを押下し続けた場合、処理を継続できるように変更しました   
 3. 視点操作でのTrackIRの優先度を低く変更しました。Hatスイッチ(POV)による操作が割り当てられボタン入力されている場合、そちらの値を優先します  
 4. TrackIRの接続がない場合、視点が中心になるように修正しました  
 5. 軸設定の削除を行えるように変更しました  https://github.com/silkyskyj/YSFLIGHT/issues/4  
 6. 軸の選択ダイアログで、初期スクロールバー位置を設定済みの軸位置に移動するように変更しました  https://github.com/silkyskyj/YSFLIGHT/issues/5  
 7. 敵や味方の機体マーカーや距離表示を非表示にできるように設定を追加しました (これはネット対戦用の設定と同じものｗシングルプレイで出来るようにしただけです)  

 Download: https://1drv.ms/u/c/538de3d97d257b91/ERoFlj2sCeJCuheWGyMuJcsBEnZl62xcqcC6KDUGMaVp1g?e=6TVUB0  
 ( Download old version: https://1drv.ms/f/c/538de3d97d257b91/EiOeDj5cKiFHrD0n-oN-QqgBvU_SaqSHWkxIvle1J21huw?e=vVaLhD )   

 2025/09/08 TrackIR Axis is now available. It can be used to move the viewpoint (POVX, POVY, POVX180 settings).  https://github.com/silkyskyj/YSFLIGHT/issues/2   

 ![Image](https://github.com/user-attachments/assets/a9377f49-3aaa-4df2-b5e3-0fca7d050ffe)  

 ![Image](https://github.com/user-attachments/assets/ab3ffc9f-fe09-4915-ab7e-e932e283963c)  

 Download: https://1drv.ms/u/c/538de3d97d257b91/EWcHdTe8GJFGoNyK2BVwEJIBTDUwBovGbIWycgIC__TIkw?e=wGCPfR  
 ( Download old version: https://1drv.ms/f/c/538de3d97d257b91/EiOeDj5cKiFHrD0n-oN-QqgBvU_SaqSHWkxIvle1J21huw?e=vVaLhD )  

## Introduction
Thank you for downloading and flying YS Flight Simulator!

YS Flight Simulator satisfied two of my lifetime goals: (1) writing my own flight simulator, and (2) writing a software used by hundreds of thousands of people over the world.  I am always so happy to receive encouraging emails about YSFLIGHT.

This is the source code of YS Flight Simulator.  I wanted to keep it to myself a bit longer, but in reality my hands are full with too many projects now and haven't been able to work on YSFLIGHT for too long.  I admit that it would be the best for long-time YSFLIGHT fans to have access to the source code.  Please feel free to fork it and make your own version.

Microsoft Flight Simulator is a great piece of work, but I also believe it is nice to have a flight simulator that everyone can casually play during the lunch break.  That has been the concept of YSFLIGHT.  But, I put many elements that I learned from my flight training in YSFLIGHT.  I do use YSFLIGHT for practicing IFR approaches in a Cessna for myself (of course I'm not logging time for it though.)  I hope YSFLIGHT serves you well for the future!

By the way, although I haven't been able to add features to YSFLIGHT recently, I still have plans.  Eventually, I'll get back to YSFLIGHT development, and finish those features.


## Compile Instruction
Prerequisite is a compiler and cmake.

YSFLIGHT requires my public libraries to build.  Follow the steps below:

```
(In your working directory)
git clone https://github.com/captainys/public.git
git clone https://github.com/captainys/YSFLIGHT.git
cd YSFLIGHT
mkdir build
cd build
cmake ../src
cmake --build . --config Release --parallel
```

The first line of code was written in 1998.  I re-used lines from my C library that I wrote between 1998 and 1996.  I also had a distrust on C++ Standard Template Library then.  So, you see many C-like code in C++.  Also my public library has many functionality that can be covered by C++ Standard Template Library.  I'm gradually making my public library inter-operable with Standard Template Library, but not fully done, and that's not my priority now.

Also bigger mess came from the experimental support for iOS.  I had to re-write my GUI library for fully concurrent mode.

By the way, I ditched iOS support because I believe it is wrong to be forced to pay money to run my own code on my own device.  I was able to test-run my iOS app on my iPhone from XCode, but it was valid for only several days.  When I tried to show my code to my class, it was expired and was useless.  AppStore is the worst and evil idea, probably one of the biggest threat, from the freedom of programming point of view.  For the sake of security?  Don't make me laugh.  Obviosly Apple, Google, and Microsoft want to kill free software.  Or, they figured security is a good excuse to exterminate us.

If Apple, Google, and Microsoft want to kill all free software, the user should be allowed to choose another application store that is more open and friendly to individual developers.  Sure, there is a danger of malicious software.  Then, have two computers, one for fun, keep all sensitive information out, and the other for your banking, shopping, and work-related communications.

I included iOS project in this repository, but I think it doesn't compile any more.

I wanted to clean the source code more before releasing, but it is what it is.

You may find strange to see CMakeFiles files in many places in this repository.  When I started using cmake, I accidentally typed cmake command from the wrong directory and contaminated my source tree very often.  By having CMakeFiles, it prevented cmake from making a directory and prevented the contamination.  Now I am used to cmake, so it is very rare to accidentally contaminate my source tree, but I am just keeping those CMakeFiles files.
