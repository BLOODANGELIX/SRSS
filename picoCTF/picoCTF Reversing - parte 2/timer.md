## Descripción del reto
You will find the flag after analysing this apkDownload [here](https://artifacts.picoctf.net/c/449/timer.apk).

## Solución

```bash
┌──(kali㉿kali)-[~/picoCTF/reversing/parte-2]
└─$ wget https://artifacts.picoctf.net/c/449/timer.apk       
--2025-11-12 12:10:11--  https://artifacts.picoctf.net/c/449/timer.apk
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.26, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4678467 (4.5M) [application/octet-stream]
Saving to: ‘timer.apk’

timer.apk                               100%[============================================================================>]   4.46M  1.22MB/s    in 3.7s    

2025-11-12 12:10:37 (1.22 MB/s) - ‘timer.apk’ saved [4678467/4678467]

┌──(kali㉿kali)-[~/picoCTF/reversing/parte-2]
└─$ unzip timer.apk  
Archive:  timer.apk
  inflating: META-INF/com/android/build/gradle/app-metadata.properties  
  inflating: classes3.dex            
  inflating: classes2.dex            
  inflating: AndroidManifest.xml     
  inflating: res/anim/abc_fade_in.xml  
  inflating: res/anim/abc_fade_out.xml  
  inflating: res/anim/abc_grow_fade_in_from_bottom.xml  
  inflating: res/anim/abc_popup_enter.xml  
  inflating: res/anim/abc_popup_exit.xml  
  inflating: res/anim/abc_shrink_fade_out_from_bottom.xml  
  inflating: res/anim/abc_slide_in_bottom.xml  
  inflating: res/anim/abc_slide_in_top.xml  
  inflating: res/anim/abc_slide_out_bottom.xml  
  inflating: res/anim/abc_slide_out_top.xml  
  inflating: res/anim/abc_tooltip_enter.xml  
  inflating: res/anim/abc_tooltip_exit.xml  
  inflating: res/anim/btn_checkbox_to_checked_box_inner_merged_animation.xml  
  inflating: res/anim/btn_checkbox_to_checked_box_outer_merged_animation.xml  
  inflating: res/anim/btn_checkbox_to_checked_icon_null_animation.xml  
  inflating: res/anim/btn_checkbox_to_unchecked_box_inner_merged_animation.xml  
  inflating: res/anim/btn_checkbox_to_unchecked_check_path_merged_animation.xml  
  inflating: res/anim/btn_checkbox_to_unchecked_icon_null_animation.xml  
  inflating: res/anim/btn_radio_to_off_mtrl_dot_group_animation.xml  
  inflating: res/anim/btn_radio_to_off_mtrl_ring_outer_animation.xml  
  inflating: res/anim/btn_radio_to_off_mtrl_ring_outer_path_animation.xml  

┌──(kali㉿kali)-[~/picoCTF/reversing/parte-2]
└─$ grep -rw picoCTF .
grep: ./classes3.dex: binary file matches

┌──(kali㉿kali)-[~/picoCTF/reversing/parte-2]
└─$ strings -t x classes3.dex | grep picoCTF
   160f *picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}
```

picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}
## Notas


## Referencia
