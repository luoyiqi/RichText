# Rich TextView

A rich TextView for Android,it can hold the pictures loading and some normal tags in TextView.

Using [Volley Library](sdsd) in picture loading part;

##ScreenShot

## Setup

**Maven**


    <repositories>
		<repository>
		    <id>jitpack.io</id>
		    <url>https://jitpack.io</url>
		</repository>
	</repositories>
	

	<dependency>
	    <groupId>com.github.moonChenHaohui</groupId>
	    <artifactId>android_richtext</artifactId>
	    <version>2.0</version>
	</dependency>

**Gradle**

	repositories {
			maven { url "https://jitpack.io" }
	}

	dependencies {
	        compile 'com.github.moonChenHaohui:android_richtext:2.0'
	}

##Usage

**XML** 


Add the com.github.moon.RichText to your layout XML file.

	<ScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:scrollbars="none">
        <com.github.moon.RichText
            android:id="@+id/rich_view"
            android:layout_width="match_parent"
            android:layout_height="match_parent"/>
    </ScrollView>
the best way is add a ScrollView around RichText
    
**init**



**1.realize OnTextViewClickListener**  
you should realize the listener for url link and pictures link : <code>OnTextViewClickListener</code> ,so that you can hold the click functions.  




	richText.setOnTextViewClickListener(new OnTextViewClickListener() {
            @Override
            public void imageClicked(ArrayList<String> arrayList, int i) {
                toast("click image,url:" + arrayList.get(i));

            }

            @Override
            public void textLinkClicked(String s) {
                toast("click link ,url:" + s);
            }
        });
        

**2.realize loadAdapter**  
realize loadAdapter you can replace the loading and error pictures when loading if have pictures. 
 
        richText.setImageLoadAdapter(new HtmlRemoteImageGetter.Adapter() {
            @Override
            public Drawable getDefaultDrawable() {
                return getDrawable(R.mipmap.load);
            }

            @Override
            public Drawable getErrorDrawable() {
                return getDrawable(R.mipmap.ic_launcher);
            }
        });
if you don't care this part ,you can ignore that.
        
**3 .setText**  
use this function to setText,otherwise it does not work

		richText.setRichText(info);
	
## Other
if you like this library，please give me an star.
	