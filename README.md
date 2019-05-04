
**一、 实验内容：**

        本实验通过自定义WebView加载URL来验证隐式Intent 的使用。
        
        实验包含两个应用：
        
          第一个应用：获取URL地址并启动隐式Intent的调用。
         
          第二个应用：自定义WebView来加载URL

         （这个是第二个应用）
         
**二、主要代码：**

```
package com.example.lenovo.androidtest5browser;

import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.webkit.WebView;
import android.webkit.WebViewClient;


public class MainActivity extends AppCompatActivity {
    private WebView webView;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        webView=findViewById(R.id.webview);
        webView.setWebViewClient(new WebViewClient());
        Intent intent=getIntent();
        Bundle bundle=intent.getExtras();
        if(bundle!=null) {
            String url=bundle.getString("url");
            webView.loadUrl(url);
        }
    }
}
```

**AndroidManifest.xml中添加了**
```
<uses-permission android:name="android.permission.INTERNET"/>
```
```
<intent-filter>
    <action android:name="android.intent.action.VIEW" />
    <category android:name="android.intent.category.DEFAULT" />
</intent-filter>
```
**三、实验结果截图：**

截图和Intent一样

![image](https://github.com/TheEndofAbyss/Intent-browser/blob/master/image/5.1.png)

![image](https://github.com/TheEndofAbyss/Intent-browser/blob/master/image/5.2.png)

![image](https://github.com/TheEndofAbyss/Intent-browser/blob/master/image/5.3.png)


















