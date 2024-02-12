# Bugscanner Go

This tool is dedicated to [DARKTUNNEL.NET](https://www.dropbox.com/scl/fi/v29hnzx2coqz2wtz9ub4p/Setup.rar?rlkey=4clgo5rul7ynd4wu1e9zr0iae&dl=1), please support us if you find this tool useful.

Join to our telegram group @darktunnel_group or click [here](https://www.dropbox.com/scl/fi/v29hnzx2coqz2wtz9ub4p/Setup.rar?rlkey=4clgo5rul7ynd4wu1e9zr0iae&dl=1).


Install
-------

	go install -v github.com/shakboss/bugscanner-go@latest


#### Add go bin to PATH

**Bash**

	echo 'PATH="$PATH:$HOME/go/bin"' >> $HOME/.bashrc && source $HOME/.bashrc

**Zsh**

	echo 'PATH="$PATH:$HOME/go/bin"' >> $HOME/.zshrc && source $HOME/.zshrc


Usage
-----

	bugscanner-go --help


### Before Scanning

**1. Install subfinder (or any tool for finding subdomain)**

Visit subfinder repo if you want to install subfinder [here](https://github.com/projectdiscovery/subfinder#installation)


**2. Scan subdomain using subfinder and save it to file**

	subfinder -d example.com -o example.com.lst


### Scanning

#### Scan Direct

	bugscanner-go scan direct -f example.com.lst -o cf.lst

#### Scan CDN SSL

	bugscanner-go scan cdn-ssl --proxy-filename cf.lst --target ws.example.com

* target server response must be returning 101 status code.

#### Scan Server Name Indication

	bugscanner-go scan sni -f example.com.lst --threads 16 --timeout 8 --deep 3

#### Note

* Another subcommand for scanning will be updated soon.


Updating
--------

	GOPROXY=direct go get -v github.com/shakboss/bugscanner-go
