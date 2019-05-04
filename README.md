
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

**AndroidManifest.xml**
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

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190504131350147.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzkwMTY5OA==,size_16,color_FFFFFF,t_70)


![在这里插入图片描述](https://img-blog.csdnimg.cn/20190504131416997.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzkwMTY5OA==,size_16,color_FFFFFF,t_70)



![在这里插入图片描述](https://img-blog.csdnimg.cn/20190504131439196.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzkwMTY5OA==,size_16,color_FFFFFF,t_70)



















