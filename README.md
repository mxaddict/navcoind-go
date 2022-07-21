navcoind
===========

A Golang client library wrapping the navcoind JSON RPC API


Installation
-----
	$ go get https://github.com/navcoin/navcoind-go


Usage
----

	package main

	import (
		"github.com/navcoin/navcoind-go"
		"log"
	)

	const (
		SERVER_HOST        = "You server host"
		SERVER_PORT        = port (int)
		USER               = "user"
		PASSWD             = "passwd"
		USESSL             = false
		WALLET_PASSPHRASE  = "WalletPassphrase"
	)

	func main() {
		bc, err := navcoind.New(SERVER_HOST, SERVER_PORT, USER, PASSWD, USESSL)
		if err != nil {
			log.Fatalln(err)
		}

		//walletpassphrase
		err = bc.WalletPassphrase(WALLET_PASSPHRASE, 3600)
		log.Println(err)

		// backupwallet
		err = bc.BackupWallet("/tmp/wallet.dat")
		log.Println(err)


		// dumpprivkey
		privKey, err := bc.DumpPrivKey("1KU5DX7jKECLxh1nYhmQ7CahY7GMNMVLP3")
		log.Println(err, privKey)

	}
	
Mores examples in example.go (in examples folder) 

Documentation
-----
Click on the button below to access the full documentation:

[![GoDoc](https://godoc.org/github.com/navcoin/navcoind-go?status.png)](https://godoc.org/github.com/navcoin/navcoind-go)	



Unit tests
----
[![Build Status](https://travis-ci.org/navcoin/navcoind-go.svg)](https://travis-ci.org/navcoin/navcoind-go)

More than 100 unit tests are made.

To run tests:

	$ go get github.com/onsi/ginkgo/ginkgo
	$ go get github.com/onsi/gomega
	$ ginkgo

	Running Suite: Navcoind Suite	
	=============================
	Random Seed: 1401120770
	Will run 112 of 112 specs

	•••••••••••••••••••••••••••••••••••
	Ran 112 of 112 Specs in 0.001 seconds
	SUCCESS! -- 112 Passed | 0 Failed | 0 Pending | 0 Skipped PASS

	Ginkgo ran in 10.856335553s
	Test Suite Passed
 



Todo
-----
* GetBlockTemplate
* sendrawtransaction
* signrawtransaction
* submitblock

##### Note on SSL support 

Note on ssl support : navcoind library doesn't verify the server's certificate chain. That means that it accepts any certificate presented by the server and any host name in that certificate. In this mode, TLS is susceptible to man-in-the-middle attacks.


Donation
------

![Donation QR](http://api.qrserver.com/v1/create-qr-code/?size=200x200&data=bitcoin:1HgpsmxV52eAjDcoNpVGpYEhGfgN7mM1JB%3Flabel%3DToorop)

[1HgpsmxV52eAjDcoNpVGpYEhGfgN7mM1JB](http://tinyurl.com/mccsoez)
