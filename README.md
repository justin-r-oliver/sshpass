# OTP code support for sshpass

This fork of the [sshpass repository](https://sourceforge.net/projects/sshpass/) adds support to bypass OTP prompts. See [feature request](https://sourceforge.net/p/sshpass/feature-requests/5/)

This fork of sshpass can be used bypass a secondary password prompt (e.g. OTP codes) in a similar way to how normal password prompts are bypassed: If a OTP code is specified using the argument '-c', then this code will be entered in response to the prompt 'Verification code:'.

### Example usage

Create a SSH connection to a host that prompts for a OTP code based on the key 'GTY6LIRKAER6RLCX':

~~~~
$ sshpass -p 'mypassword' -c `oathtool --base32 --totp GTY6LIRKAER6RLCX` ssh user@host
~~~~

The example assumes that the [OATH Toolkit](http://www.nongnu.org/oath-toolkit/) has been installed.

### Future enhancements

Respond to secondary password prompts besides 'Verification code:' e.g. 'One-time password (OATH) for `user':', as specified using a '-P2' argument.

### Build steps

1. ./bootstrap
2. ./configure
3. make

