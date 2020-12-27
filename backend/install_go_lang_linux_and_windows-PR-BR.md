
## Como instalar o **Go Lang** em máquinas *Linux* e *Windows* :

Go é uma linguagem de programação que nasceu da frustração no Google. Os desenvolvedores precisavam escolher continuamente uma linguagem que fosse executada com eficiência, mas demoravam muito tempo para compilar ou escolher uma linguagem fácil de programar, mas que era executada de forma ineficiente em produção. O Go foi projetado para ter todas as três características disponíveis ao mesmo tempo: compilação rápida, facilidade de programação e execução eficiente em produção.

Instalando no Linux Ubuntu 18.04:

``` sudo apt-get update ```

``` sudo apt-get upgrade ```

Quando o terminal estiver aberto, você instalará manualmente os binários do Go. Embora você possa usar um gerenciador de pacotes, percorrer as etapas de instalação manual o ajudará a entender as alterações de configuração necessárias ao sistema para ter um workspace Go válido.

Use o *curl* para recuperar a URL do tarball que você copiou da página oficial de downloads do Go:

``` curl -O https://dl.google.com/go/go1.12.1.linux-amd64.tar.gz  ```


Em seguida:

``` sha256sum go1.12.1.linux-amd64.tar.gz ```

O hash que é exibido a partir da execução do comando acima deve corresponder ao hash que estava na página de downloads. Se não, então este não é um arquivo válido e você deve baixar o arquivo novamente.

``` 
Output
2a3fdabf665496a0db5f41ec6af7a9b15a49fbe71a85a50ca38b1f13a103aeec  go1.12.1.linux-amd64.tar.gz ``` 



Referência:
https://golang.org/