# gpg-agent-windows
***to avoid passphrase prompt in command line***
1. go to cmd and write -> **gpgconf --list-dirs**. It will give a list of directories from there you have to choose the statring with "homedir",
2. Then go to the directory and create a file named **gpg-agent.conf** add this lines on to the file 
"
**verbose
allow-preset-passphrase**
"
and save the file.
3. Then kill gpg agent by typing **gpgconf --kill gpg-agent** into the cmd.

4. get the keygrip -> **gpg --with-keygrip --list-secret-keys** (# to list the keygrip)

5. create the gpg-agent cache -> **gpg-connect-agent "preset_passphrase 6266A0D194C88B84773659094B47BE969233DFA7 -1 5040353577307264" /bye**
here the format is -- gpg-connect-agent "preset_passphrase "keygrip" [timeout] "passphrase in hex format" [-1 = infinity time]
