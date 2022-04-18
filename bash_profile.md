alias gi="git init"
alias gcg="git config --global"
alias ga="git add"
alias gs="git status"
alias gc="git commit -m"
alias gp="git push"
alias gl="git pull"
alias gcl="git clone"
alias gd="git diff"
alias gf="git fetch"
alias gst="git stash"
alias gct="git checkout"
alias gb="git branch"
alias gcp="git cherry-pick"

# git stash
# git cherry-pick

# Generator Stuff
alias pa="php artisan"
alias pas="php artisan serve"
alias pam="php artisan migrate"
alias pau="php artisan up"
alias pad="php artisan down"
alias pasp="php artisan serve --port="
alias pas="php artisan serve"
alias pamm="php artisan make:migration"
alias pami="php artisan migrate:install"
alias padbs="php artisan db:seed"
alias pat="php artisan tinker"
alias m:m="php artisan make:mdoel"
alias m:e="php artisan make:event"
alias m:j="php artisan make:job"
alias m:c="phpartisan make:controller"
alias m:r="php artisan make:request"
alias m:s="php artisan make:seed"
alias m:sr="php artisan make:seeder"
alias m:l="php artisan make:listener"
alias m:mw="php artisan make:middleware"
alias m:p="php artisan make:provider"

alias g:m="php artisan generate:model"
alias g:c="php artisan generate:controller"
alias g:v="php artisan generate:view"
alias g:s="php artisan generate:seed"
alias g:mig="php artisan generate:migration"
alias g:r="php artisan generate:resource"

alias pu="vendor/bin/phpunit"
alias puc="vendor/bin/phpunit --coverage-html dir"

# Git branch in prompt.

parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

export PS1="\u@\h \W\[\033[32m\]\$(parse_git_branch)\[\033[00m\] $ "



# Mac .ZSHRC
# Load version control information
autoload -Uz vcs_info
precmd() { vcs_info }

# Format the vcs_info_msg_0_ variable
zstyle ':vcs_info:git:*' formats 'on branch %b'
 
# Set up the prompt (with git branch name)
setopt PROMPT_SUBST
PROMPT='%n in ${PWD/#$HOME/~} ${vcs_info_msg_0_} > '
