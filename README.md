# go_jolokia

```
< go_jolokia >
 --------
   \
    \   
       _____  -----------------  _____
      |     \/  ----     ----  \/     |
       \  ==/  /    |   |    \  \==  /
        \--/  | ()  |   |()   |  \--/
          /    \---/ ___ \---/    \
         |         _(===)_         |
        |         (__/--\__)        |
         |          |_||_|         |
          \                       /   
```

go_jolokia is a Simple jolokia JMX/HTTP wrapper for Go. It supports jolokia proxy setup as well as direct host connection.

[![GoDoc](https://img.shields.io/badge/api-Godoc-blue.svg?style=flat-square)](https://godoc.org/github.com/swarvanusg/go_jolokia)

### Version
0.1.0

### Usage

#### Step 1 : Get It
To get the go_jolokia install Go and execute the below command 
```
go get github.com/swarvanusg/go_jolokia
```

#### Step 2 : Initiate a client
```go
client := NewJolokiaClient("http://" + proxyhost + ":" + proxyport + "/" + jolokia)

client.SetTarget(targetHost + ":" + targetPort)
```

#### Step 3 : Use the client for Getting Info
```go
beans, err := client.ListBeans("java.lang")

props, err := client.ListProperties("java.lang", []string{"type=Threading"})

val, err := client.GetAttr("java.lang", []string{"type=Threading"}, "PeakThreadCount")
```


#### Current Status:
The go_jolokia build is success
The test cases are passing 

#### Inspired from
github.com/cmceniry/golokia 
