# Yowsup Setup

Setup instructions for [yowsup][yowsup] (A python whatsapp library).

### Platform
All of this was tested on an Ubuntu 14.04 machine but should work across all Linux flavours.

## Installation

 - Requires python2.6+, or python3.0 +
 - Required python packages: python-dateutil,
 - Required python packages for end-to-end encryption: protobuf, pycrypto, python-axolotl-curve25519
 - Required python packages for yowsup-cli: argparse, readline (or pyreadline for windows), pillow (for sending images)

Best way to install is by using pip:

```
pip install yowsup2
```
You can also install using setup.py to install all the python dependencies.

```
python setup.py install
```


# Configuration.

```
yowsup-cli registration --requestcode sms --phone 234xxxxxxxxxx --cc 234 --mcc 621 --mnc 60
```
After this, the code will then be delivered to your mobile phone number via your preferred method (SMS/voice). Once you have obtained the code, you  proceed with the second step, which is to send that code using the '--register' argument. This example will consider the received code  as being 123-456
```
yowsup-cli registration --register 123-456 --phone 234xxxxxxxxxx --cc 234
```
Configuration Options

  - --mcc (Mobile  Country Code)
  - --mnc (Mobile  Network Code)
  - --cc  (Country Code)
  -  --phone: The  full phone number including the country code defined in 'cc', without preceding '+' or '00'.


Check your mcc and mnc using this [list][mcclist]

## Usage

  - replace CREDENTIALS object in run.py with credentials gotten from configuration step above.
  - start the simple http server using the command below
```
python server.py
```

   [yowsup]: <https://github.com/tgalal/yowsup>
   [mcclist]: <http://mcclist.com/mobile-network-codes-country-codes.asp>


