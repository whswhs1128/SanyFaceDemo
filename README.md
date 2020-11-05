# SanyFaceDemo
sany android screen facedemo and display video demo apk

三一智能15.6寸安卓中控屏宝马展演示程序
视频播放+人脸识别demo

人脸识别demo程序：
基于arcsoft demo程序改写，默认进入视频识别界面，将FaceAttrPreviewActivity作为main intent。启动自动设置360度感应，自动激活sdk操作。完成无感启动开始人脸360度识别功能。


视频播放：
适配1080p分辨率屏幕，全屏循环播放res/test.mp4文件。为三一智能大屏演示视频。

11.5更新：
1.修改默认main intent为视频播放PlayVideoActivity，启动apk后默认播放视频。以免分辨率不对情况下，屏幕出现白边。
        
        <activity
            android:name=".activity.PlayVideoActivity"
            android:launchMode="singleTop" >
        <intent-filter>
            <action android:name="android.intent.action.MAIN" />

            <category android:name="android.intent.category.LAUNCHER" />
        </intent-filter>

2.播放视频默认横屏，达到全屏效果。
        if(getRequestedOrientation()!= ActivityInfo.SCREEN_ORIENTATION_LANDSCAPE){
            setRequestedOrientation(ActivityInfo.SCREEN_ORIENTATION_LANDSCAPE);
        }
 
        android:screenOrientation="landscape">
        
3.添加切换按钮，play video/face detect。将两个单独apk写为一个apk，完成按键切换，以供11.20宝马展演示用。
    public void playVideo(View view) {
        startActivity(new Intent(this, PlayVideoActivity.class));
    }
    
        <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="bottom|end"
        android:layout_margin="@dimen/common_bottom_margin"
        android:onClick="playVideo"
        android:text="@string/play_video" />
    
    public void faceDetect(View view) {
        startActivity(new Intent(this, FaceAttrPreviewActivity.class));
    }
    
        <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="bottom|end"
        android:layout_margin="@dimen/common_bottom_margin"
        android:onClick="faceDetect"
        android:text="@string/face_detect" />


