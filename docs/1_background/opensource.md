# Software Overview

##  Components and libraries.

![](..\images\techstack.png)



#### Codebases and Dependencies 

![](..\images\048-venonat.png) : DEV environment

![](..\images\049-venomoth.png) : PROD environment, stable



Our [Open source Libraries](https://github.com/lorena-ssi)

- [lorena-doc](https://github.com/lorena-ssi/lorena-doc) : This documentation

- [credentials-lib](https://github.com/lorena-ssi/credential-lib) : Library to interact with Verifiable Credentials

- [zenroom-lib](https://github.com/lorena-ssi/zenroom-lib) : zenroom-lib is a javascript library to interact with the Zenroom Virtual Machine.

- [matrix-lib](https://github.com/lorena-ssi/matrix-lib) : matrix-lib is a caelum api for matrix connection used in Lorena SSI.

- [substrate-lib](https://github.com/lorena-ssi/substrate-lib): is an api for Substrate used in `Lorena SSI`

- [terminal](https://github.com/lorena-ssi/terminal) : Client to manage idspaces

- [lorena-sdk](https://github.com/lorena-ssi/lorena-sdk): Client library for interacting with Lorena identities

- [wallet-lib](https://github.com/lorena-ssi/wallet-lib): Default implementation has simple POSIX filesystem-based storage useful for console applications and tests

  

## Deployed instances



|            | WHERE THE CODE IS (OPEN-SOURCE)                        | WHERE IT IS DEPLOYED: DEV ENVIRONMENT ![](..\images\048-venonat.png) | WHERE IT IS DEPLOYED: PROD ENVIRONMENT![](..\images\049-venomoth.png) |
| :--------- | :----------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| BLOCKCHAIN | [substrate-node](https://github.com/)                  | lorena.substrate.test.caelumlabs.com                         | lorena.substrate.caelumlabs.com                              |
| SDK        | [Lorena sdk](https://github.com/lorena-ssi/lorena-sdk) | (not)                                                        | (not)                                                        |
| DEMO APP   | demo-client                                            | [demo.app](https://lorena.app.test.caelumlabs.com/)          | [demo](https://lorena.app.caelumlabs.com)                    |