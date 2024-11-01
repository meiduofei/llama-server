# just run the code below
fn = 'llama-server'  
zipff=fn+'.zip'  
zipf='https://github.com/meiduofei/llama-server/raw/main/'+zipff  
if not os.path.exists('server'):  
&nbsp;&nbsp;&nbsp;!wget -q -c $zipf  
&nbsp;&nbsp;&nbsp;!unzip -q -o $zipff  
&nbsp;&nbsp;&nbsp;!mv $fn server  
&nbsp;&nbsp;&nbsp;!chmod 777 ./server  
\# !chmod 777 ./server  
