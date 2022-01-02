Chirp is maintained at https://chirp.danplanet.com but the code is written in python2. He has a link to convert to python3 at https://chirp.danplanet.com/projects/chirp/wiki/Linux_Python3.

Instructions are for Ubuntu not for Fedora. 

  $ apt-get install -y python3-gi python3-six python3-serial gir1.2-gtk-3.0 mercurial
 
  $ hg clone http://d-rats.com/hg/chirp.hg
  
  $ cd chirp.hg
  
  $ hg update py3
  
  $ python3 chirpw
  
  
My steps to change 
  $ sudo dnf install python3-gobject (this is a substitue for python3-gi.} This was already installed. 
Found out python3-six was also installed but python3-serial and gir1.2.gtk-3.0 were not found. Found python3-pyserial package and installed that and mercurial.
  $ sudo dnf install python3-pyserial mercurial
gir1.2-gtk-3.0 wasn't found but discovered it's part of the gtk package. 
I tried to see if I could run everything without downloading the gir1.2-gtk-3.0 package. 
  $ cd $HOME/source
  $ cd chirp.hg
  $ hg update py3
  147 files updated, 0 files merged, 54 files removed, 0 files unresolved  
  $ python chirpw
Traceback (most recent call last):
  File "/home/xxxxxxx/source/chirp.hg/chirpw", line 35, in <module>
    from chirp import chirp_common
  File "/home/xxxxxxx/source/chirp.hg/chirp/chirp_common.py", line 17, in <module>
    from future import standard_library
ModuleNotFoundError: No module named 'future'
Ok so found the future library and installed that.
  $ pip install future
  $ python chirpw
Failed to import chirp.hg/chirp/drivers/baofeng_uv3r: multiple exception types must be parenthesized (baofeng_uv3r.py, line 54)
Failed to import chirp.hg/chirp/drivers/ap510: multiple exception types must be parenthesized (ap510.py, line 383)
Failed to import chirp.hg/chirp/drivers/fd268: multiple exception types must be parenthesized (fd268.py, line 793)
Failed to import chirp.hg/chirp/drivers/bf-t1: multiple exception types must be parenthesized (bf-t1.py, line 228)
Failed to import chirp.hg/chirp/drivers/ft2800: multiple exception types must be parenthesized (ft2800.py, line 204)
Failed to import chirp.hg/chirp/drivers/bjuv55: multiple exception types must be parenthesized (bjuv55.py, line 650)
Failed to import chirp.hg/chirp/drivers/ft2d: multiple exception types must be parenthesized (ft1d.py, line 1893)
Failed to import chirp.hg/chirp/drivers/ft7100: multiple exception types must be parenthesized (ft7100.py, line 571)
Failed to import chirp.hg/chirp/drivers/ft8100: Missing parentheses in call to 'print'. Did you mean print(...)? (ft8100.py, line 178)
Failed to import chirp.hg/chirp/drivers/ft50: multiple exception types must be parenthesized (ft50.py, line 589)
Failed to import chirp.hg/chirp/drivers/ftm3200d: multiple exception types must be parenthesized (ft1d.py, line 1893)
Failed to import chirp.hg/chirp/drivers/ft1d: multiple exception types must be parenthesized (ft1d.py, line 1893)
Failed to import chirp.hg/chirp/drivers/ft90: multiple exception types must be parenthesized (ft90.py, line 335)
Failed to import chirp.hg/chirp/drivers/ftm350: multiple exception types must be parenthesized (ftm350.py, line 281)
Failed to import chirp.hg/chirp/drivers/ft70: multiple exception types must be parenthesized (ft70.py, line 1165)
Failed to import chirp.hg/chirp/drivers/kguv8dplus: multiple exception types must be parenthesized (kguv8dplus.py, line 421)
Failed to import chirp.hg/chirp/drivers/kguv9dplus: multiple exception types must be parenthesized (kguv9dplus.py, line 880)
Failed to import chirp.hg/chirp/drivers/kyd_IP620: multiple exception types must be parenthesized (kyd_IP620.py, line 184)
Failed to import chirp.hg/chirp/drivers/kguv8d: multiple exception types must be parenthesized (kguv8d.py, line 379)
Failed to import chirp.hg/chirp/drivers/th7800: multiple exception types must be parenthesized (th7800.py, line 539)
Failed to import chirp.hg/chirp/drivers/th_uv3r25: multiple exception types must be parenthesized (wouxun.py, line 277)
Failed to import chirp.hg/chirp/drivers/puxing_px888k: can only concatenate list (not "range") to list
Failed to import chirp.hg/chirp/drivers/thd72: multiple exception types must be parenthesized (thd72.py, line 584)
Failed to import chirp.hg/chirp/drivers/tk270: 'float' object cannot be interpreted as an integer
Failed to import chirp.hg/chirp/drivers/ts2000: Missing parentheses in call to 'print'. Did you mean print(...)? (ts2000.py, line 220)
Failed to import chirp.hg/chirp/drivers/th_uv3r: multiple exception types must be parenthesized (wouxun.py, line 277)
Failed to import chirp.hg/chirp/drivers/ts590: multiple exception types must be parenthesized (ts590.py, line 1647)
Failed to import chirp.hg/chirp/drivers/ts850: 'dict' object has no attribute 'iteritems'
Failed to import chirp.hg/chirp/drivers/vx6: multiple exception types must be parenthesized (vx6.py, line 874)
Failed to import chirp.hg/chirp/drivers/wouxun: multiple exception types must be parenthesized (wouxun.py, line 277)
Failed to import chirp.hg/chirp/drivers/vxa700: multiple exception types must be parenthesized (vxa700.py, line 180)
Failed to import chirp.hg/chirp/drivers/alinco: multiple exception types must be parenthesized (alinco.py, line 202)
Failed to import chirp.hg/chirp/drivers/anytone: multiple exception types must be parenthesized (anytone.py, line 180)
Failed to import chirp.hg/chirp/drivers/anytone_ht: multiple exception types must be parenthesized (anytone_ht.py, line 236)
Failed to import chirp.hg/chirp/drivers/baofeng_common: multiple exception types must be parenthesized (baofeng_common.py, line 167)
Failed to import chirp.hg/chirp/drivers/baofeng_wp970i: multiple exception types must be parenthesized (baofeng_common.py, line 167)
Failed to import chirp.hg/chirp/drivers/bj9900: multiple exception types must be parenthesized (bj9900.py, line 181)
Failed to import chirp.hg/chirp/drivers/ft2900: multiple exception types must be parenthesized (ft2900.py, line 540)
Failed to import chirp.hg/chirp/drivers/ft450d: multiple exception types must be parenthesized (ft450d.py, line 502)
Failed to import chirp.hg/chirp/drivers/ft60: multiple exception types must be parenthesized (ft60.py, line 406)
Failed to import chirp.hg/chirp/drivers/gmrsuv1: multiple exception types must be parenthesized (baofeng_common.py, line 167)
Failed to import chirp.hg/chirp/drivers/kguv8e: multiple exception types must be parenthesized (kguv8e.py, line 340)
Failed to import chirp.hg/chirp/drivers/kyd: multiple exception types must be parenthesized (kyd.py, line 503)
Failed to import chirp.hg/chirp/drivers/leixen: multiple exception types must be parenthesized (leixen.py, line 264)
Failed to import chirp.hg/chirp/drivers/lt725uv: multiple exception types must be parenthesized (lt725uv.py, line 1396)
Failed to import chirp.hg/chirp/drivers/mursv1: multiple exception types must be parenthesized (baofeng_common.py, line 167)
Failed to import chirp.hg/chirp/drivers/puxing: multiple exception types must be parenthesized (puxing.py, line 50)
Failed to import chirp.hg/chirp/drivers/radioddity_r2: multiple exception types must be parenthesized (radioddity_r2.py, line 614)
Failed to import chirp.hg/chirp/drivers/radtel_t18: multiple exception types must be parenthesized (radtel_t18.py, line 481)
Failed to import chirp.hg/chirp/drivers/retevis_rt1: multiple exception types must be parenthesized (retevis_rt1.py, line 729)
Failed to import chirp.hg/chirp/drivers/retevis_rt21: multiple exception types must be parenthesized (retevis_rt21.py, line 564)
Failed to import chirp.hg/chirp/drivers/retevis_rt22: multiple exception types must be parenthesized (retevis_rt22.py, line 608)
Failed to import chirp.hg/chirp/drivers/retevis_rt23: multiple exception types must be parenthesized (retevis_rt23.py, line 849)
Failed to import chirp.hg/chirp/drivers/retevis_rt26: multiple exception types must be parenthesized (retevis_rt26.py, line 900)
Failed to import chirp.hg/chirp/drivers/rfinder: multiple exception types must be parenthesized (rfinder.py, line 243)
Failed to import chirp.hg/chirp/drivers/rh5r_v2: Missing parentheses in call to 'print'. Did you mean print(...)? (rh5r_v2.py, line 170)
Failed to import chirp.hg/chirp/drivers/tdxone_tdq8a: multiple exception types must be parenthesized (tdxone_tdq8a.py, line 304)
Failed to import chirp.hg/chirp/drivers/th9000: multiple exception types must be parenthesized (th9000.py, line 355)
Failed to import chirp.hg/chirp/drivers/th9800: multiple exception types must be parenthesized (th9800.py, line 601)
Failed to import chirp.hg/chirp/drivers/th_uv8000: multiple exception types must be parenthesized (th_uv8000.py, line 1489)
Failed to import chirp.hg/chirp/drivers/thuv1f: multiple exception types must be parenthesized (thuv1f.py, line 217)
Failed to import chirp.hg/chirp/drivers/tk760: 'float' object cannot be interpreted as an integer
Failed to import chirp.hg/chirp/drivers/tk760g: multiple exception types must be parenthesized (tk760g.py, line 910)
Failed to import chirp.hg/chirp/drivers/ts480: multiple exception types must be parenthesized (ts480.py, line 1141)
Failed to import chirp.hg/chirp/drivers/uv5x3: multiple exception types must be parenthesized (baofeng_common.py, line 167)
Failed to import chirp.hg/chirp/drivers/uv6r: multiple exception types must be parenthesized (baofeng_common.py, line 167)
Failed to import chirp.hg/chirp/drivers/vgc: multiple exception types must be parenthesized (vgc.py, line 1413)
Traceback (most recent call last):
  File "chirp.hg/chirpw", line 139, in <module>
    from chirp.ui import mainapp
  File "chirp.hg/chirp/ui/mainapp.py", line 1140
    print query
    ^^^^^^^^^^^
SyntaxError: Missing parentheses in call to 'print'. Did you mean print(...)?

This means the code wasn't converted. 
Ran 2to3 on the first file and the errors went away. 
  $ 2to3 -w chirp.hg/chirp/drivers/baofeng_uv3r.py
Now for the whole directory: 
  $ 2to3 -w chirp.hg/chirp/drivers/*.py
  $ python chirpw
Failed to import chirp.hg/chirp/drivers/ft70: module 'string' has no attribute 'uppercase'
Failed to import chirp.hg/chirp/drivers/ft90: module 'string' has no attribute 'uppercase'
Failed to import chirp.hg/chirp/drivers/tk270: 'float' object cannot be interpreted as an integer
Failed to import chirp.hg/chirp/drivers/tk760g: 'float' object cannot be interpreted as an integer
Failed to import chirp.hg/chirp/drivers/tk760: 'float' object cannot be interpreted as an integer
Traceback (most recent call last):
  File "/home/xxxxxxx/source/chirp.hg/chirpw", line 139, in <module>
    from chirp.ui import mainapp
  File "/home/xxxxxxx/source/chirp.hg/chirp/ui/mainapp.py", line 1140
    print query
    ^^^^^^^^^^^
SyntaxError: Missing parentheses in call to 'print'. Did you mean print(...)?

Those drivers will need to be fixed. 
