# Android Image Slider 



# 说明

本项目fork自 [https://github.com/daimajia/AndroidImageSlider](https://github.com/daimajia/AndroidImageSlider)

## 对其进行一些改写:



图片加载组件改成fresco.

Sliderlayout增加动态更新的方法:用于设置数据和刷新数据

```
refreshSlider(List<SliderInfo> datas, BaseSliderView.OnSliderClickListener listener)
```

设置图片大小(用于服务器压缩和向下采样)
```
public void setImageDimension(int width,int height)
```



解决了多次调用startAutoCycle() 出现快速滚动两页的bug



## 原说明

This is an amazing image slider for the Android platform. I decided to open source this because there is really not an attractive, convenient slider widget in Android.

You can easily load images from an internet URL, drawable, or file. And there are many kinds of amazing animations you can choose. :-D

## Demo

![](http://ww3.sinaimg.cn/mw690/610dc034jw1egzor66ojdg20950fknpe.gif)



## Usage

### Step 1

### gradle

Step 1. Add the JitPack repository to your build file

Add it in your root build.gradle at the end of repositories:

```
allprojects {
    repositories {
        ...
        maven { url "https://jitpack.io" }
    }
}
```

Step 2. Add the dependency

```java
dependencies {
        compile 'com.github.hss01248:ImageSliderByFresco:1.0.2'
        compile 'com.daimajia.androidanimations:library:1.0.3@aar'
          
        compile 'com.facebook.fresco:fresco:0.10.0'
    	compile 'com.facebook.fresco:animated-webp:0.10.0'
    	compile 'com.facebook.fresco:animated-gif:0.10.0'
}
```



### Step 2

Add permissions (if necessary) to your `AndroidManifest.xml`

```xml
<!-- if you want to load images from the internet -->
<uses-permission android:name="android.permission.INTERNET" /> 

<!-- if you want to load images from a file OR from the internet -->
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
```



### Step 3

Add the Slider to your layout:

```java
<com.hss01248.slider.SliderLayout
        android:id="@+id/slider"
        android:layout_width="match_parent"
        android:layout_height="200dp"
/>
```

There are some default indicators. If you want to use a provided indicator:

```java
<com.hss01248.slider.Indicators.PagerIndicator
        android:id="@+id/custom_indicator"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:gravity="center"
        />
```



### Step 4 使用封装好的刷新方法

> 添加和刷新数据:

`refreshSlider(List<SliderInfo> datas, BaseSliderView.OnSliderClickListener listener)`

> 暂停和恢复轮播



```
startAutoCycle() 

stopAutoCycle()

```



## Advanced usage

自定义动画,点的位置:

请看demo中的MainActivity

## Thanks

- [AndroidImageSlider](https://github.com/daimajia/AndroidImageSlider)

