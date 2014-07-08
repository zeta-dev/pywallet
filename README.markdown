# PyWallet


#### <span style="color:red">Just like all the tools that modify your wallet, it may (unlikely because it is heavily tested before being released) corrupt your wallet, so you must be sure that you have a copy of your wallet in a vault to avoid any wallet loss.</span>
#### Also, you have to close Bitcoin/Zetacoin wallet before using Pywallet.

## Help
Usage: pywallet.py [options]

Options:
    --version             show program's version number and exit 
    -h, --help            show this help message and exit
    --passphrase=PASSPHRASE
                        passphrase for the encrypted wallet
    --dumpwallet          dump wallet in json format
    --dumpwithbalance     includes balance of each address in the json dump,
                        takes about 2 minutes per 100 addresses
    --importprivkey=KEY   import private key from vanitygen
    --importhex           KEY is in hexadecimal format
    --datadir=DATADIR     wallet directory (defaults to bitcoin default)
    --wallet=WALLETFILE   wallet filename (defaults to wallet.dat)  
    --label=LABEL         label shown in the adress book (defaults to '')
    --testnet             use testnet subdirectory and address type
    --namecoin            use namecoin address type
    --otherversion=OTHERVERSION
                        use other network address type, whose version is
                        OTHERVERSION
    --info                display pubkey, privkey (both depending on the
                        network) and hexkey
    --reserve             import as a reserve key, i.e. it won't show in the
                        adress book
    --multidelete=MULTIDELETE
                        deletes data in your wallet, according to the file
                        provided
    --balance=KEY_BALANCE
                        prints balance of KEY_BALANCE
    --web                 run pywallet web interface
    --port=PORT           port of web interface (defaults to 8989)
    --recover             recover your deleted keys, use with recov_size and
                        recov_device
    --recov_device=RECOV_DEVICE
                        device to read (e.g. /dev/sda1 or E: or a file)
    --recov_size=RECOV_SIZE
                        number of bytes to read (e.g. 20Mo or 50Gio)
    --recov_outputdir=RECOV_OUTPUTDIR
                        output directory where the recovered wallet will be
                        put
    --clone_watchonly_from=CLONE_WATCHONLY_FROM
                        path of the original wallet
    --clone_watchonly_to=CLONE_WATCHONLY_TO
                        path of the resulting watch-only wallet
    --dont_check_walletversion
                        don't check if wallet version > 81000 before running
                        (WARNING: this may break your wallet, be sure you know
                        what you do)
    --wait=NSECONDS       wait NSECONDS seconds before launch


## Requirements

    Python 2.5-2.7
    bsddb package: necessary to open wallets
    twisted package: necessary if you want to use the web interface
    ecdsa package: necessary if you want to sign and verify messages



## Dependencies

Debian-based Linux:
 aptitude install build-essential python-dev python-twisted python-bsddb3

Mac OS X:
 1. Install MacPorts from http://www.macports.org/
 2. sudo port install python27 py27-twisted py27-pip py-bsddb python_select
 3. sudo port select --set python python27
 4. sudo easy_install ecdsa

Windows: 
 1. Install Python 2.7
 2. Install Twisted 11.0.0 for Py2.7, then Zope.Interface (a .egg file) for Py2.7: http://twistedmatrix.com/trac/wiki/Downloads

 3. Untested, proposed by TeaRex: install Zope.Interface from http://www.lfd.uci.edu/~gohlke/pythonlibs

 If this doesn't work, you will have to install the egg file:

 3(32bit). http://pypi.python.org/pypi/setuptools#downloads to install setuptools
 3(64bit). http://pypi.python.org/pypi/setuptools#windows to download, then run ez_setup.py

 4. Go to C:\Python27\Scripts
 5. Run easy_install.exe zope.interface-3.6.4-py2.7-win-amd64.egg


## Installation

Linux/OSX

    Open a terminal in pywallet folder and type "./pywallet.py --web"
    Browse http://localhost:8989

Windows

    Download https://github.com/downloads/jackjack-jj/pywallet/PWI_0.0.3.exe (SHA256: 645a4d092733ad6685de730a38b210c6594e44a15690a87a231859477deca316)
    Run it
    Click about a thousand times on Yes/Next/I Agree/OK
    Go to the directory where you extracted it and run pywallet.bat
    Browse http://localhost:8989


## Other Usage Case (works on GNU/Linux and Mac too)

##### Starting PyWallet Web Interface with DataDir and Passphrase
``` ./pywallet.py --datadir=~/some-directory --passphrase=PASS --web ```

##### Dump my Wallet from a different DataDir, addr_pub version set to 80 (Zetacoin) and Passphrase, to a file named dump.json
``` ./pywallet.py --datadir=~/some-directory --otherversion=80 --passphrase=PASS --dumpwallet > ~/dump.json ```

##### For other Usage Case check <a href="http://pywallet.tk/">http://pywallet.tk/</a>

