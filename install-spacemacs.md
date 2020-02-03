# Install Spacemacs for Go

## Introduction

Goal is to use Spacemacs for Go (Golang) with:

- Go layer
- Using Go modules
- Fully working LSP and LSP-ui
- DAP support with LSP using, Delve, Node.js and VSCode plugin
- LSP flycheck and golangci-lint for linting and extended error checking
- Organise imports on save
- Format buffer on save

## Install from scratch

These steps are tested on both MacOs and Ubuntu. The installation is very similar and the only steps that are different are the installation steps of Golang and Emacs.

### Pre-requisites

- Git
- Homebrew

## Reference pages

[https://github.com/syl20bnr/spacemacs](https://github.com/syl20bnr/spacemacs)

[https://develop.spacemacs.org/layers/+lang/go/README.html](https://develop.spacemacs.org/layers/+lang/go/README.html)

[https://develop.spacemacs.org/layers/+tools/lsp/README.html](https://develop.spacemacs.org/layers/+tools/lsp/README.html)

## Steps:

1. Install Golang 

    ```bash
            brew install golang
    ```
    **Important** : for everything to function, both the go installation as the go variables should be reachable from $PATH variable. Updating you rc file is essential.
    Update your .profile .bashrc .zshrc .zshenv etc. with:

    ```bash
        # set Golang paths
        export GOPATH=$HOME/go
        export GOBIN=$HOME/go/bin
        # set both path to PATH
        export PATH=$PATH:$GOPATH:$GOBIN:/usr/local/opt/go/libexec/bin
    ``` 
    **Note:** the location where Go is installed is different on every OS. The example above is for MacOs. For Ubuntu this can be:  
    ```bash
    export PATH=$PATH:$GOPATH:$GOBIN:/usr/local/go/bin
    ```
    After sourcing the file you edited, go should be available from every folder. 

    Make sure these folders exist in your home folder.
    ```bash
        cd ~
        mkdir go
        cd go
        mkdir src bin pkg
    ```

2. Follow directions on this page to install Emacs: [https://github.com/syl20bnr/spacemacs#macos](https://github.com/syl20bnr/spacemacs#macos)

    ```bash
        brew tap d12frosted/emacs-plus
        brew install emacs-plus
        brew linkapps emacs-plus
    ```

    If `brew linkapps emacs-plus` does not work, try:
    ```bash
        ln -s /usr/local/Cellar/emacs-plus/*/Emacs.app/ /Applications/
    ```
    To install emacs26 on Ubuntu
    ```bash
    sudo add-apt-repository ppa:kelleyk/emacs
    sudo apt-get update
    sudo apt install emacs26
    ```
3. Install font Source Code Pro: [Link to github](https://github.com/adobe-fonts/source-code-pro#font-installation-instructions)
    
4. Install Spacemacs
    ```bash
        git clone https://github.com/syl20bnr/spacemacs ~/.emacs.d
    ```

    Do not open Spacemacs just yet! First checkout in the `develop` branch.
    ```bash
        git checkout develop
    ```

5. Install all Go goodies required for everything to work.
Make sure to checkout this page: [Link to Spacemacs Go layer](https://develop.spacemacs.org/layers/+lang/go/README.html)

    ```bash
        cd ~/go
        
        GO111MODULE=on go get -v golang.org/x/tools/gopls@latest
        go get -u -v golang.org/x/tools/cmd/godoc
        go get -u -v golang.org/x/tools/cmd/goimports
        go get -u -v golang.org/x/tools/cmd/gorename
        go get -u -v github.com/cweill/gotests/...
        go get -u -v github.com/davidrjenni/reftools/cmd/fillstruct
        go get -u -v github.com/fatih/gomodifytags
        go get -u -v github.com/godoctor/godoctor
        go get -u -v github.com/golangci/golangci-lint/cmd/golangci-lint
        go get -u -v github.com/haya14busa/gopkgs/cmd/gopkgs
        go get -u -v github.com/josharian/impl
        go get -u -v github.com/mdempsky/gocode
        go get -u -v github.com/rogpeppe/godef
        go get -u -v github.com/zmb3/gogetdoc
    ```

    Install Delve (needed for dap)
    ```bash
        go get -u github.com/go-delve/delve/cmd/dlv
    ```

    Install node.js (needed for dap)
    ```bash
        brew install nodejs
    ```
    > Note: installing node.js was not necessary on Ubuntu.

    Check if everything is installed
    ```bash
        ➜  ~ go version
        go version go1.13.3 darwin/amd64
        ➜  ~ emacs --version
        GNU Emacs 26.2
        Copyright (C) 2019 Free Software Foundation, Inc.
        GNU Emacs comes with ABSOLUTELY NO WARRANTY.
        You may redistribute copies of GNU Emacs
        under the terms of the GNU General Public License.
        For more information about these matters, see the file named COPYING.
        ➜  ~ dlv version
        Delve Debugger
        Version: 1.3.2
        Build: $Id: 569ccbd514fc47c8b4c521b142556867ec5e6917 $
        ➜  ~
        ➜  ~ golangci-lint version
        golangci-lint has version 1.22.2 built from cb2f8ba on 2019-12-30T19:26:28Z
        ➜  ~ node --version
        v13.5.0
    ```

    In the go/bin folder there should be (at least) the following files
    ```bash
        ➜  bin l
        total 353376
        drwxr-xr-x  17 macuser  staff   544B Jan 18 20:37 .
        drwxr-xr-x   5 macuser  staff   160B Jan 18 18:55 ..
        -rwxr-xr-x   1 macuser  staff    17M Jan 18 20:37 dlv
        -rwxr-xr-x   1 macuser  staff   6.5M Jan 18 18:56 fillstruct
        -rwxr-xr-x   1 macuser  staff    13M Jan 18 18:57 gocode
        -rwxr-xr-x   1 macuser  staff   9.4M Jan 18 18:57 godef
        -rwxr-xr-x   1 macuser  staff    16M Jan 18 18:55 godoc
        -rwxr-xr-x   1 macuser  staff   7.6M Jan 18 18:56 godoctor
        -rwxr-xr-x   1 macuser  staff   7.3M Jan 18 18:57 gogetdoc
        -rwxr-xr-x   1 macuser  staff   5.5M Jan 18 18:55 goimports
        -rwxr-xr-x   1 macuser  staff    35M Jan 18 18:56 golangci-lint
        -rwxr-xr-x   1 macuser  staff   4.4M Jan 18 18:56 gomodifytags
        -rwxr-xr-x   1 macuser  staff   4.9M Jan 18 18:56 gopkgs
        -rwxr-xr-x   1 macuser  staff    19M Jan 18 18:55 gopls
        -rwxr-xr-x   1 macuser  staff   6.0M Jan 18 18:55 gorename
        -rwxr-xr-x   1 macuser  staff    13M Jan 18 18:55 gotests
        -rwxr-xr-x   1 macuser  staff   5.7M Jan 18 18:56 impl
    ```

5. Start emacs
Select evil-mode and full installation
Open the .spacemacs file with `SPC f e d`
Uncomment of add these lines in the `dotspacemacs-configuration-layers`:
    ```lisp
        auto-completion
        better-defaults
        emacs-lisp
        git
        helm
        lsp
        multiple-cursors
        syntax-checking
        treemacs
        version-control
        (go :variables
            go-backend 'lsp
            go-use-golangci-lint t
            )
        dap
    ```

6. Add custom configuration

    To manage imports and format the file on save, add these lines in `dotspacemacs-user-config`
    ```lisp
        (add-hook 'before-save-hook #'lsp-format-buffer t)
        (add-hook 'before-save-hook #'lsp-organize-imports t)
        (treemacs-resize-icons 15)
        (setq lsp-ui-flycheck-enable t)
    ```

7. To enable DAP-debugging, add the following to enable dap-go to the `dotspacemacs-user-config`
   ```lisp
        (require 'dap-go)
   ```

    Add keybindings for dap/hydra for convenience
    ```lisp
        (spacemacs/set-leader-keys-for-minor-mode
            'lsp-mode-map
            "dd" #'dap-debug
            "de" #'list-flycheck-errors
            "dg" #'dap-go-setup
            "dh" #'dap-hydra
            "dr" #'dap-debug-restart
            "xa" #'go-run-dot ;;custom func
            )
    ```

8. Add golangco-lint to lsp-ui. Golangci-lint is called whenever lsp-flycheck has no errors.
In the .spacemacs file, add:
    ```lisp
        (add-hook 'lsp-after-initialize-hook (lambda
                                                 ()
                                                 (flycheck-add-next-checker 'lsp-ui '(warning . golangci-lint))))
    ```
[.spacemacs file](./.spacemacs)

## Note:

After every change, quit and restart Spacemacs to make sure changes are applied.

Remove `.emacs.d/.lsp-session-v1` to start 'fresh' and add the directory to lsp when opening the file. 

## DAP after installation
Dap has to be initialized once to install the VSCode debugger extension.  
Do that by:
```lisp
M-x dap-go-setup
```
This is `SPC SPC dap-go-setup` in evil mode of course.  

Contents of `dotspacemacs-user-config` looks like:  
```lisp

(defun dotspacemacs/user-config ()
  ;; hooks for formatting buffer and organising imports
  (add-hook 'before-save-hook #'lsp-format-buffer t)
  (add-hook 'before-save-hook #'lsp-organize-imports t)

  ;; resize treemacs icons
  (treemacs-resize-icons 15)

  ;; enable lsp-ui-flycheck
  (setq lsp-ui-flycheck-enable t)

  ;; make sure we have dap-go
  (require 'dap-go)

  ;; hook to start golangci-lint when lsp-ui-flycheck has no errors
  (add-hook 'lsp-after-initialize-hook (lambda
                                        ()
                                        (flycheck-add-next-checker 'lsp-ui '(warning . golangci-lint))))

  ;; Template to appear on top of the list
  (dap-register-debug-template "Custom default"
                              (list :type "go"
                                    :request "launch"
                                    :name "Launch File"
                                    :mode "auto"
                                    :program nil
                                    :buildFlags nil
                                    :args nil
                                    :env nil
                                    :envFile nil))

  ;; custom func to execute 'go run .'
  (defun go-run-dot ()
    (interactive)
    (shell-command
    (format "go run .")))

  ;; create and remap some key bindings for minor mode
  (spacemacs/declare-prefix-for-mode 'go-mode "md" "debug")
  (spacemacs/set-leader-keys-for-minor-mode
    'lsp-mode-map
    "dd" #'dap-debug
    "de" #'list-flycheck-errors
    "dg" #'dap-go-setup
    "dh" #'dap-hydra
    "dr" #'dap-debug-restart
    "xa" #'go-run-dot
          )
  )
```
