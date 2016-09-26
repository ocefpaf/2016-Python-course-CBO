# 2016 Python Course -- CBO

[![Build Status](https://travis-ci.org/ocefpaf/2016-Python-course-CBO.svg?branch=master)](https://travis-ci.org/ocefpaf/2016-Python-course-CBO) [![Build status](https://ci.appveyor.com/api/projects/status/dokxy0ev3h7tmp60?svg=true)](https://ci.appveyor.com/project/ocefpaf/2016-python-course-cbo) [![Binder](http://mybinder.org/badge.svg)](http://mybinder.org:/repo/ocefpaf/2016-python-course-cbo)

## TODOS OS ALUNOS DEVEM TRAZER LAPTOP PRÓPRIO E CONFIGURADO DE ACORDO COM AS INSTRUÇÕES ABAIXO ANTES DO INÍCIO DO CURSO!!!

## Instruções para instalação da distribuição Python

Recomendamos a distribuição Python [miniconda](http://conda.pydata.org/miniconda.html),
uma versão leve da distribuição Python [Anaconda](https://store.continuum.io/cshop/anaconda/),
e as instruções abaixo são escritas com ela em mente.

1. Download e instale a versão apropriada do *Miniconda installer* de http://conda.pydata.org/miniconda.html. Com o `miniconda` você pode (e deve!) criar ambientes (*conda environments*) que usam qualquer versão de Python (por exemplo Python 2.7 ou Python 3.5). Por isso Recomendamos que você instale a última versão, Python 3.5, e se mais tarde precisar de um ambiente Python 2.7, você pode simplesmente criar um. Usuários `Windows` precisam escolher entre 32-bit (em geral o bom e velho `Windows XP`) ou 64-bit (Windows modernos).

### Windows


Rode o *installer*. Escolha *For all users* ao invés de *For just myself* para que o `miniconda` seja instalado fora do espaço de usuário e,
por isso, mas facilmente configurável. Clique em ambas caixas que colocam o `miniconda` como o Python default,
e que adiciona ao *path*.

**CUIDADO 0:** Se você não tem permissão para usar *For all users*,
então os caminhos (*paths*) abaixo terão que ser editados para refletir a sua pasta!

**CUIDADO 1:** Se você usa outra distribuição Python, como ArcGIS,
você **não** pode marcar as caixas que fazem do `miniconda` o sua Python *default* nem a que adiciona no *path*.
Nesse caso você terá que procurar o ícone do *Anaconda Prompt* em "Start Menu=>All Programs=>Anaconda3.

### Linux/OS X (Ou Windows 10 bash)

Copie-e-cole:

```shell
if [[ $(uname) == "Darwin" ]]; then
  url=https://repo.continuum.io/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
elif [[ $(uname) == "Linux" ]]; then
  url=https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
fi
curl $url -o miniconda.sh
bash miniconda.sh -b
export PATH=$HOME/miniconda3/bin:$PATH
```

Recomendamos adicionar a linha abaixo no seu `~/.bashrc` para garantir que o Python do `miniconda` será o primeiro a ser encontrado no seu sistema:

```
export PATH=$HOME/miniconda3/bin:$PATH
```

## Criar um ambiente para o curso

Download o arquivo [environment.yml](https://raw.githubusercontent.com/ioos/notebooks_demos/master/environment.yml) clicando com o botão direito do *mouse* e escolha `salvar como...`,
ou, no `OS X` e `Linux`, use os comandos abaixo:

```bash
url=https://raw.githubusercontent.com/ioos/notebooks_demos/master/environment.yml
curl $url -o environment.yml
```

Navegue até a pasta em que salvou o arquivo acima,
e digite os seguintes comandos no `shell`/[`terminal`](http://stackoverflow.com/questions/378319/windows-explorer-command-prompt-here/379804):

```bash
conda config --add channels conda-forge --force
conda update --yes --all
conda env create environment.yml
```

Assim que o comando terminar de instalar tudo você poderá abrir o ambiente do curso digitando:

```bash
activate CBO2016  # Windows
source activate CBO2016  # OSX e Linux
```

e para sair digite:

```bash
deactivate  # Windows
source deactivate  # OSX e Linux
```

# Se o `miniconda` não for instalado como o seu Python default...

Se você escolher não colocar a distribuição Python `miniconda` no seu `~.bashrc` ou *path* do Windows,
você deve lembrar de sempre ativar o ambiente `miniconda` manualmente toda vez que for usar digitando:

```
C:\Miniconda3\Scripts\activate CBO2016  # Windows
export PATH=$HOME/miniconda3/bin:$PATH && source activate CBO2016  # OSX e Linux
```

## Test se tudo está instalado corretamente

TODO

PS: Alunos avançados podem tentar utilizar outras distribuições,
mas se certifiquem que conseguem rodar os exemplos ANTES do curso!
