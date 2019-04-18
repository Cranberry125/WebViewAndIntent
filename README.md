# WebViewAndIntent
lab5-2:连接网页
# 代码：
```
MainActivity.java
package com.example.webviewandintent;

import android.content.Intent;
import android.net.Uri;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity  implements View.OnClickListener{
    private Button button;
    private EditText editUrl;
    private String urlHead="http://";
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        initView();
    }
    private void initView(){
        button=(Button) findViewById(R.id.button);
        editUrl=(EditText) findViewById(R.id.edit_text);
        button.setOnClickListener(this);
    }
    @Override
    public void onClick(View view){
        switch (view.getId()){
            case R.id.button:
                Intent intent=new Intent();
                intent.setAction("android.intent.action.VIEW");
                intent.setData(Uri.parse(urlHead+editUrl.getText().toString()));
                startActivity(Intent.createChooser(intent, "请选择浏览器"));
                break;
        }
    }


}

activity_main.java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/edit_text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:textSize="30sp"
        android:hint="请输入网址"
        android:layout_weight="1" />
    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="访问" />

</LinearLayout>
```



# 运行截图：
![4655BFF4BE080BFDCD60C6F143B13606.jpg](https://i.loli.net/2019/04/18/5cb897fbe9185.jpg)
![579BD9513A36AC5DF62130AC4A934D37.jpg](https://i.loli.net/2019/04/18/5cb8980013d97.jpg)
![BF787D52E48D95F81316C8B832082035.jpg](https://i.loli.net/2019/04/18/5cb89802efb1c.jpg)

