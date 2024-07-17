# Preparação de Ambiente de Trabalho com LaTeX usando WSL

Preparação Ambiente de Trabalho com LaTeX em Windows com WSL.

## Instalar o Visual Studio Code

## Instalar as Fontes - Nerd Fonts (FiraCode Nerd Font)

## Instalação e Configuração do WSL

* Executar o Windows Terminal.
* Instalação do WSL.

~~~powershell
wsl --install --no-distribution
~~~

* Finalizada instalação reiniciar o computador.

~~~powershell
shutdown -r -t 00
~~~

* Atualizar o WSL.

~~~powershell
wsl --update
~~~

* Definir a versão 2 do WSL.

~~~powershell
wsl --set-default-version 2
~~~

* Verificar as distribuições do GNU/Linux disponíveis.

~~~powershell
wsl --list --online
~~~

* Instalar a distribuição do GNU/Linux.

~~~powershell
wsl --install --distribution ubuntu-24.04
~~~

* Criação do usuário e senha do GNU/Linux.

* Finalizada instalação da distribuição será necessário criar um usuário e senha para acessar o sistema.

* Sair do GNU/Linux e Definir a distribuição padrão do GNU/Linux.

~~~powershell
exit
~~~

~~~powershell
wsl --set-default ubuntu-24.04
~~~

* Verificar as distribuições instaladas.

~~~powershell
wsl --list --verbose
~~~

## Configuração do VS Code

* Abrir o VS Code e instalar a extensão WSL.
* Reiniciar o VS Code.
* Conectar VS Code na Distro no WSL.

Será instalado o VS Code Server no WSL.

## Instalação das Extensões do VS Code

* Realizar a instalação das extensões:

1. Dracula Official
2. Material Icon Theme
3. Code Spell Checker
4. Brazilian Portuguese - Code Spell Checker
5. EditorConfig for VS Code
6. LaTeX Workshop
7. LaTeX Utilities
8. Markdown All in One
9. markdownlint
10. Path Intellisense
11. Reload

## Configuração das preferencias do VS Code

1. Abrir o VS Code;
2. Abrir o Visual Studio Code;
3. Com o comando "Ctrl + Shift + p" abrir a Command Palette;
4. Buscar a opção: Preferences:Open User Settings (JSON);
5. Substituir as configurações do JSON.

~~~json
{
    "workbench.activityBar.location": "hidden",
    "workbench.colorTheme": "Dracula",
    "workbench.iconTheme": "material-icon-theme",
    "workbench.layoutControl.enabled": false,
    "workbench.startupEditor": "none",
    "breadcrumbs.enabled": false,
    "cSpell.language": "en,pt_BR",
    "editor.bracketPairColorization.enabled": true,
    "editor.fontFamily": "'FiraCode Nerd Font'",
    "editor.fontLigatures": true,
    "editor.fontSize": 14,
    "editor.formatOnPaste": true,
    "editor.formatOnSave": true,
    "editor.insertSpaces": true,
    "editor.minimap.enabled": false,
    "editor.renderLineHighlight": "gutter",
    "editor.renderWhitespace": "boundary",
    "editor.scrollbar.horizontal": "hidden",
    "editor.scrollbar.vertical": "hidden",
    "editor.smoothScrolling": true,
    "editor.suggestSelection": "recentlyUsedByPrefix",
    "editor.wordWrap": "off",
    "editor.wrappingIndent": "indent",
    "explorer.compactFolders": false,
    "files.trimTrailingWhitespace": true,
    "git.autofetch": true,
    "terminal.integrated.defaultProfile.linux": "zsh",
    "terminal.integrated.fontFamily": "FiraCode Nerd Font",
    "terminal.integrated.fontSize": 14,
    "window.commandCenter": false,
    "latex-workshop.intellisense.package.enabled": true,
    "latex-workshop.kpsewhich.bibtex.enabled": true,
    "latex-workshop.latex.autoBuild.run": "onSave",
    "latex-workshop.latex.autoClean.run": "onFailed",
    "latex-workshop.latex.clean.subfolder.enabled": true,
    "latex-workshop.latex.external.build.args": [
        "--shell-escape",
        "--synctex=1",
        "--interaction=nonstopmode",
        "--file-line-error",
        "--halt-on-error"
    ],
    "latex-workshop.latex.recipe.default": "latexmk (lualatex)",
    "latex-workshop.latex.recipes": [
        {
            "name": "latexmk (lualatex)",
            "tools": [
                "lualatexmk"
            ]
        }
    ],
    "latex-workshop.latex.tools": [
        {
            "name": "lualatexmk",
            "command": "latexmk",
            "args": [
                "--lualatex",
                "--shell-escape",
                "--synctex=1",
                "--interaction=nonstopmode",
                "--file-line-error",
                "--halt-on-error",
                "%DOC%"
            ]
        }
    ],
    "latex-workshop.linting.chktex.enabled": true,
    "latex-workshop.linting.run": "onType",
    "latex-workshop.synctex.afterBuild.enabled": true,
    "latex-workshop.texdoc.args": [
        "--view",
        "--shell-escape"
    ],
    "latex-workshop.view.pdf.viewer": "tab",
}
~~~

## Instalação e configuração do Zsh

## Instalação do Zsh

Abrir Terminal do VS Code:

Abrir o Windows Terminal ou Terminal do VS Code:

* Instalar pacotes de desenvolvimento.

~~~bash
sudo apt install build-essential -y
~~~

* Instalar o Zsh.

~~~bash
sudo apt install zsh -y
~~~

* Após a instalação do zsh realizar a mudança do shell:

~~~bash
chsh -s /bin/zsh
~~~

* Iniciar o zsh:

~~~bash
zsh
~~~

Reiniciar o Windows Terminal ou Terminal do VS Code para iniciar o shell Zsh.

## Instalação do Oh My Zsh

* Instalar o Oh My Zsh:

~~~bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
~~~

## Instalar e configurar o plugin zsh-autosuggestions

* Configuração do plugin zsh-autosuggestions:

~~~bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
~~~

Adicionar o plugin na lista de plugins do Oh My Zsh (no arquivo ~/.zshrc):

~~~bash
zsh-autosuggestions
~~~

## Instalar e configurar zsh-syntax-highlighting

* Configuração do plugin zsh-syntax-highlighting:

~~~bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
~~~

Adicionar o plugin na lista de plugins do Oh My Zsh (no arquivo ~/.zshrc):

~~~bash
zsh-syntax-highlighting
~~~

## Instalação e configuração do tema spaceship

* Configuração do tema spaceship:

~~~bash
git clone https://github.com/spaceship-prompt/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt" --depth=1
~~~

~~~bash
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
~~~

Configurar o tema no arquivo (no arquivo ~/.zshrc):

~~~bash
ZSH_THEME="spaceship"
~~~

Após a configuração você vai realizar a configuração do visual do shell.

## Instalação do MikTeX

* Registro da chave GPG:

~~~bash
curl -fsSL https://miktex.org/download/key | sudo tee /usr/share/keyrings/miktex-keyring.asc > /dev/null
~~~

* Configurar source.list:

~~~bash
echo "deb [signed-by=/usr/share/keyrings/miktex-keyring.asc] https://miktex.org/download/ubuntu jammy universe" | sudo tee /etc/apt/sources.list.d/miktex.list
~~~

* Instalação do MikTeX:

~~~bash
sudo apt update -y && sudo apt install miktex -y
~~~

* Finalizar a configuração.

~~~bash
sudo miktexsetup --shared=yes finish
~~~

* Habilitar a instalação automática de pacote.

~~~bash
sudo initexmf --admin --set-config-value '[MPM]AutoInstall=1'
~~~

* Atualização dos pacotes.

~~~bash
sudo mpm --verbose --update
~~~

* Encerrar terminal e Reiniciar VS Code;
* Iniciar novo terminal.

Realizar upgrade dos pacotes via GUI - Usuário Administrador.

~~~bash
sudo miktex-console --admin
~~~

* Instalar pacotes CPAN:

~~~bash
sudo cpan YAML::Tiny
~~~

~~~bash
sudo cpan File::HomeDir
~~~

## Configuração do Git

~~~bash
git config --global user.name "username"
~~~

~~~bash
git config --global user.email email@dominio
~~~

~~~bash
git config --global user.editor code
~~~
