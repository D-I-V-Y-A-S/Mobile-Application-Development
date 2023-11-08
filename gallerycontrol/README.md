# Ex.No:8 To create a gallery control using android studio to display images or photos.


### AIM:
```
To create a gallery control using android studio to display images or photos.
```

### EQUIPMENTS REQUIRED:
```
Latest Version Android Studio
```

### ALGORITHM:
```
Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as HelloWorld and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Insert the required images in the res->drawable folder.

Step 7: Complete the necessary coding in MainActivity and CustomizedGalleryAdapter file.

Step 8: Save and run the application.
```

### PROGRAM:
```
/*
Program to print the text “GalleryControl”.
Developed by: DIVYA S
Registeration Number : 212221040043
*/
```

### MainActivity.java
```
package com.example.gallery_view;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

import android.widget.Gallery;

import android.view.View;

import android.widget.AdapterView;

import android.widget.Gallery;

import android.widget.ImageView;

public class MainActivity extends AppCompatActivity {
    Gallery simpleGallery;
    
    CustomizedGalleryAdapter customGalleryAdapter;
    
    ImageView selectedImageView;
    
    int[] images = {R.drawable.bird, R.drawable.bt21,R.drawable.bts,R.drawable.grin};
    
    @Override
    protected void onCreate(Bundle savedInstanceState) {
    
        super.onCreate(savedInstanceState);
        
        setContentView(R.layout.activity_main);
        
        simpleGallery = (Gallery) findViewById(R.id.languagesGallery);
        
        selectedImageView = (ImageView) findViewById(R.id.imageView);
        
        customGalleryAdapter = new CustomizedGalleryAdapter(getApplicationContext(), images);
        
        simpleGallery.setAdapter(customGalleryAdapter);
        
        simpleGallery.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
            
                selectedImageView.setImageResource(images[position]);
            }
        });
    }
}
```
### CustomizedGalleryAdapter.java:
```
package com.example.gallery_view;

import android.content.Context;

import android.view.View;

import android.view.ViewGroup;

import android.widget.BaseAdapter;

import android.widget.Gallery;

import android.widget.ImageView;

public class CustomizedGalleryAdapter extends BaseAdapter {
    private Context context;
    
    private int[] images;
    
    public CustomizedGalleryAdapter(Context c, int[] images) {
        context = c;
        
        this.images = images; }
    public int getCount() {
        return images.length; }
    public Object getItem(int position) {
        return position;  }
    public long getItemId(int position) {
        return position;  }
    public View getView(int position, View convertView, ViewGroup parent) {
        ImageView imageView = new ImageView(context);
        imageView.setImageResource(images[position]);
        imageView.setLayoutParams(new Gallery.LayoutParams(200, 200));
        return imageView;
    }
}
```

### activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="36dp"
        app:layout_constraintBottom_toTopOf="@+id/languagesGallery"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:srcCompat="@tools:sample/avatars" />

    <Gallery
        android:id="@+id/languagesGallery"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="171dp"
        android:layout_marginBottom="204dp"
        android:animationDuration="2000"
        android:padding="10dp"
        android:spacing="5dp"
        android:unselectedAlpha="50"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

### OUTPUT

![image](https://github.com/Pavishmi/Mobile-Application-Development/assets/136091280/bfa62727-7cd0-4a40-ad84-edf05a9ee625)


### RESULT

Thus a Simple Android Application to create a gallery control using android studio to display images or photos is developed and executed successfully.
