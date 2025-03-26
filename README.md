Just run the code below:
```
import os
fn = 'llama-server'
zipff=fn+'.zip'
zipf='https://github.com/meiduofei/llama-server/raw/main/'+zipff
if not os.path.exists('llama-server'):
    !wget -q -c $zipf
    !unzip -q -o $zipff
    !chmod 777 ./llama-server
```
```
def run_server(param):
    import os
    import subprocess

    pos, port = param
    p = subprocess.Popen(
        [
            "./llama-server",
            "-m",
            f"{model_dir}/{MODEL}",
            "-ngl",
            "99",
            "-c",
            "4096",
            "-a",
            MODEL.removesuffix(".guff"),
            "--port",
            port,
        ],
        env={**os.environ, "CUDA_VISIBLE_DEVICES": str(pos)} if DOUBLE else None,
        stdout=subprocess.PIPE,
        stderr=subprocess.STDOUT,
        encoding="utf8",
        bufsize=0,
    )
    while True:
        for line in p.stdout:
            if line.startswith("{"):
                message = format_message(line)
                print(f"{pos}-{port} {message}")
            else:
                print(f"{pos}-{port} {line}", end="")
```
