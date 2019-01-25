We want to change the cloud platform which our production environment used these days. 
Hyperledger Fabric Orders module has some problem when block data migrated.
So I review the code of Orders:), hope this can figure out some problem.

First function Main() 

 There are two dependent packages [kingpin](https://godoc.org/gopkg.in/alecthomas/kingpin.v2) and 
 [viper](https://godoc.org/github.com/spf13/viper)
 which deal with the command line and config.
