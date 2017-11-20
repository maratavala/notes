#### Prevent verification of self signed certificate while using xmlrpc library in Python

#### Method1 (Python3). Change context  
import ssl  
from xmlrpc import client  
  
ctx=ssl.create_default_context()  
ctx.check_hostname = False  
ctx.verify_mode = ssl.CERT_NONE  
  
myclient = client.ServerProxy(uri='https://<server_name>/rpc/api', verbose=False, context=ctx)  

#### Method2 (Python2.7). Monkey patch ssl attribute   
import ssl  
import xmlrpc  

if hasattr(ssl, '_create_unverified_context'):  
&nbsp;&nbsp;&nbsp;&nbsp; sssl._create_default_https_context = ssl._create_unverified_context  
