# just run the code below
fn = 'llama-server'  
zipff=fn+'.zip'  
zipf='https://github.com/meiduofei/llama-server/raw/main/'+zipff  
if not os.path.exists('server'):  
    !wget -q -c $zipf  
    !unzip -q -o $zipff  
    !mv $fn server  
    !chmod 777 ./server  
!chmod 777 ./server  
