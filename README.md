<p align="center">
  <a href="" rel="wsl">
 <img width=300px height=200px src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQNc0EUBpf7OZsQIPhaEBxSfDI6FpyhsyhnsQ&usqp=CAU" alt="Project logo"></a>
</p>

<h3 align="center">WSL Custom</h3>

<!-- <div align="center">

[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![GitHub Issues](https://img.shields.io/github/issues/kylelobo/The-Documentation-Compendium.svg)](https://github.com/kylelobo/The-Documentation-Compendium/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/kylelobo/The-Documentation-Compendium.svg)](https://github.com/kylelobo/The-Documentation-Compendium/pulls)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

</div> -->

---

<p align="center">
    <br> 
</p>

## 📝 Conteúdo

- [Sobre](#about)
- [Configurando o WSL](#config)
- [Configurando o ZSH e Oh-My-Zsh](#zsh)

## 🧐 Sobre <a name = "about"></a> <p>

Subsistema do Windows para Linux vem com o sistema operacional Windows, mas você deve habilitá-lo e instalar uma distribuição do Linux antes de começar a usá-lo. <br>

Para usar o comando simplificado --install, você deve estar executando um build recente do Windows (Build 20262+). Para verificar a sua versão e o número de build, selecione a tecla do logotipo do Windows + R, digite winver e selecione OK. Você pode atualizar usando o menu Configurações ou o Assistente de Windows Update. <br>

Se você preferir instalar uma distribuição do Linux diferente do Ubuntu ou preferir concluir essas etapas manualmente, consulte a página de instalação do WSL para obter mais detalhes. <br><br>

## ⚙️ Configurando o WSL <a name = "config"></a> <p>

Quem utiliza o WSL sabe que conforme formos consumindo recursos como memória RAM e CPU, ele irá alocar o quanto ele achar que precisa, podendo deixar o Windows com falta de recursos conforme iniciamos aplicações, containers, etc. <br>

Um ponto essencial após instalar o WSL e subir uma distribuição nele é configurar o limite de uso de memória. Para isto, crie, caso ainda não existe, o arquivo wsl.conf dentro do diretório do perfil de seu usuário no windows, normalmente em C:\Users\[Usuario]. No Powershell, podemos abrir o arquivo com o comando a seguir:

````
notepad "$env:USERPROFILE/.wslconfig"
````
<br>

Vamos adicionar o seguinte conteúdo ao arquivo, que já vou explicar a seguir:

```
[wsl2]
memory=3GB   # Limita a memória da VM no WSL 2 até 3 GB
processors=4 # Faz com que a VM do WSL 2 use dois processadores virtuais
#swap= opicional
```
<br>
Memory: limite de memória que poderá ser utilizada pela máquina virtual do WSL. Recomenda-se sempre deixar uma quantidade mínima de 3–4GB para o SO principal, então se você tiver 8GB de RAM, recomendo um limite de 3–4gb de uso para o WSL. Caso tenha 16GB, um limite de 8GB será mais que o suficiente.

<br>
Processors: limite a quantidade de núcleos virtuais do processador o WSL poderá utilizar. Caso tenha um processador como um Intel i5 9th geração ou superior, recomenda-se a limitar para 4 núcleos no máximo. Caso tenha um i7 de 9th geração ou superior, limites como até 8 núcleos podem ser utilizados sem problemas.

<br>

Após salvar o arquivo, no Prompt de Comando ou Powershell, execute o comando a seguir:

````
wsl --shutdown <distro_wsl_instalada> #Ex: Ubuntu 20.04
````

<br>
Existem outras configurações além dos limites de memória e uso de núcleos virtuais do processador, que podem ser encontradas no link a seguir, mas as essenciais a serem definidas são uso de memória e núcleos.

<a href="https://learn.microsoft.com/pt-br/windows/wsl/wsl-config#wsl-2-settings">configurações avançadas no WSL </a>

## ⌨️  Configurando o ZSH e Oh-My-Zsh <a name = "zsh"></a> <p>

O Oh-My-Zsh facilita ativar vários plugins úteis no dia-a-dia, como auto-complete e suporte ao git, docker, npm, .net e outros. <br>
Nesse vídeo do Fabio Akita ele traz a instalacao do ZSH e define ele como Shell padrão <a href="https://www.youtube.com/watch?v=sjrW74Hx5Po">O Melhor Setup Dev com Arch e WSL2</a>

