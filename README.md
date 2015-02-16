# ionicons-for-android
Codes to use ionicons in android textviews

Inspired by https://github.com/liltof/font-awsome-for-android, codes calculated using this script:

    grep "\f" variables.less | awk -F\" '{ print $1 $2 ";</string>" }' | sed 's/\\/\&#x/' | sed 's/@/<string           name=\"icon_/' | sed 's/:\ /\">/' | sed 's/-/_/g'

taken from http://www.eldelshell.com/font-awesome-icons-in-android.html.

# How to use
Put the .ttf of ionicons in the assets folder of your android project. Then refer to the string as in the example below after loading the right typeface at runtime:

    <TextView
    android:id="@+id/textView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="@string/icon_ionicon_var_volume_mute"
    android:textSize="18sp" />


    TextView txt = (TextView) findViewById(R.id.textView);  
    Typeface font = Typeface.createFromAsset(getAssets(), "ionicons.ttf");
    txt.setTypeface(font);