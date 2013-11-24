" vim: set foldmarker={,} foldlevel=0 foldmethod=marker:

" Basic Settings {

" Mine {
set guifont=Menlo:h19
"set double byte character
set guifontwide=Hei_Regular:h20
"set single byte character
set guioptions=egrL
colorscheme lucius
"g:lucius_style='dark'
set background=dark
set mouse=a
" }

set nocompatible
"set term=xterm
set t_Co=256
set wildmode=longest,list,full
set wildmenu
" }

" Vundle Settings {
" To Install Vundle:
" git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle
" vim +BundleInstall +qall
filetype off
set rtp+=~/.vim/bundle/vundle/
call vundle#rc()
Bundle 'gmarik/vundle'
" Custom Plugins {
Bundle 'mattn/webapi-vim'
Bundle 'mattn/gist-vim'
Bundle 'vimwiki'
Bundle 'plasticboy/vim-markdown'
Bundle 'ShowMarks'
Bundle 'chetui/unique-tagdb'
Bundle 'The-NERD-tree'
Bundle 'winmanager'
Bundle 'taglist.vim'
Bundle 'cscope.vim'
Bundle 'SrcExpl'
Bundle 'Smart-Home-Key'
Bundle 'SingleCompile'
Bundle 'bufexplorer.zip'
Bundle 'a.vim'
Bundle 'Cpp11-Syntax-Support'
Bundle 'Lokaltog/vim-powerline'
Bundle 'tpope/vim-surround'
Bundle 'kien/ctrlp.vim'
Bundle 'MarcWeber/vim-addon-mw-utils'
Bundle "tomtom/tlib_vim"
Bundle "honza/snipmate-snippets"
Bundle 'garbas/vim-snipmate'
Bundle 'godlygeek/tabular'
Bundle 'altercation/vim-colors-solarized'
Bundle 'jdevera/vim-protobuf-syntax.git'
Bundle 'Shougo/neocomplcache'
Bundle 'git://vim-latex.git.sourceforge.net/gitroot/vim-latex/vim-latex'
" }
filetype plugin indent on
" }

" Plugin: gist-vim {
" let g:gist_use_password_in_gitconfig = 1
let g:gist_clip_command = 'pbcopy'
let g:gist_show_privates = 1
let g:gist_post_private = 1
let g:gist_get_multiplefile = 1
let g:gist_open_browser_after_post = 1
" }

" Plugin: cscope {
if has("cscope")
  set csprg=/opt/local/bin/cscope
  set csto=1
  set cst
  set nocsverb
  " add any database in current directory
"  if filereadable("cscope.out")
"      cs add cscope.out
"  endif
  set csverb
  set cscopequickfix=s-,c-,d-,i-,t-,e-
endif

nmap <C-@>s :cs find s <C-R>=expand("<cword>")<CR><CR>:copen<CR>
nmap <C-@>g :cs find g <C-R>=expand("<cword>")<CR><CR>
nmap <C-@>c :cs find c <C-R>=expand("<cword>")<CR><CR>:copen<CR>
nmap <C-@>t :cs find t <C-R>=expand("<cword>")<CR><CR>:copen<CR>
nmap <C-@>e :cs find e <C-R>=expand("<cword>")<CR><CR>:copen<CR>
nmap <C-@>f :cs find f <C-R>=expand("<cfile>")<CR><CR>:copen<CR>
nmap <C-@>i :cs find i ^<C-R>=expand("<cfile>")<CR>$<CR>:copen<CR>
nmap <C-@>d :cs find d <C-R>=expand("<cword>")<CR><CR>:copen<CR>
" }

" File related {
set fileencodings=ucs-bom,utf-8,cp936,gb18030,big5,euc-jp,euc-kr,latin1
set autochdir
set hidden
set undodir=~/.vim/undodir/
set undofile
set tags+=tags;
set grepprg=grep\ -nH\ $*
set shellslash
" }

"   UI related {
set ruler
set showmatch
set hlsearch
set linebreak
set number
set visualbell
set cursorcolumn
set cursorline
set mouse=a
set mousemodel=popup
"autocmd VimEnter * set ttymouse=xterm2
"autocmd FocusGained * set ttymouse=xterm2
"autocmd BufEnter * set ttymouse=xterm2
"colo darkmate
"let g:solarized_termcolors=256
"colo solarized
"set background=dark
"if (has("gui_running"))
"    set guioptions=egrL guifont=Monaco\ 11 lines=40 columns=80 nowrap
"else
"    set wrap
"endif
" }

" Edit related {
set backspace=indent,eol,start
set whichwrap=b,s,<,>,[,]
set selectmode=
set selection=exclusive
set keymodel=startsel,stopsel
map <C-c> "+y<CR>
map! <C-v> <C-r>+
" }

" Syntax related { 
syntax on
let g:load_doxygen_syntax=1
set tabstop=4 shiftwidth=4
set smarttab
set expandtab
set cindent cinoptions=:0g0t0(susj1N-s
set autoindent
set linebreak ambiwidth=double
set formatoptions+=mB
" }

" Plugin: winmanager {
" should fix bug!: add exec 'q' in following position:
"      function! <SID>ToggleWindowsManager()
"        if IsWinManagerVisible()
"           call s:CloseWindowsManager()
"        else
"           call s:StartWindowsManager()
"           exe 'q'
"        end
"     endfunction
let g:NERDTree_title="[NERDTree]"
let g:winManagerWindowLayout="NERDTree|TagList"
let g:winManagerWidth = 10
"let g:AutoOpenWinManager = 1
let g:defaultExplorer = 0

function! NERDTree_Start()
    exec 'NERDTree'
endfunction

function! NERDTree_IsValid()
    return 1
endfunction

nmap <C-W><C-F> :FirstExplorerWindow<cr>
nmap <C-W><C-B> :BottomExplorerWindow<cr>
nmap wm :WMToggle<CR>
" }

" Plugin: ctags_cscope_refresh {
nmap <C-@><C-f> :UniqueTagDBRefreshFile <CR>
nmap <C-@><C-c> :UniqueTagDBRefreshCon <CR>
nmap <C-@><C-s> :cs show <CR>
" }

" Plugin: Source Explorer {
" // The switch of the Source Explorer 
nmap ee :SrcExplToggle<CR> 

" // Set the height of Source Explorer window 
let g:SrcExpl_winHeight = 8 

" // Set 100 ms for refreshing the Source Explorer 
let g:SrcExpl_refreshTime = 100 

" // Set "Enter" key to jump into the exact definition context 
" let g:SrcExpl_jumpKey = "<ENTER>" 

" // Set "Space" key for back from the definition context 
let g:SrcExpl_gobackKey = "<SPACE>" 

" // In order to Avoid conflicts, the Source Explorer should know what plugins 
" // are using buffers. And you need add their bufname into the list below 
" // according to the command ":buffers!" 
let g:SrcExpl_pluginList = [ 
        \ "__Tag_List__", 
        \ "_NERD_tree_", 
        \ "Source_Explorer" 
    \ ] 

" // Enable/Disable the local definition searching, and note that this is not 
" // guaranteed to work, the Source Explorer doesn't check the syntax for now. 
" // It only searches for a match with the keyword according to command 'gd' 
let g:SrcExpl_searchLocalDef = 1 

" // Do not let the Source Explorer update the tags file when opening 
let g:SrcExpl_isUpdateTags = 1 

" // Use 'Exuberant Ctags' with '--sort=foldcase -R .' or '-L cscope.files' to 
" //  create/update a tags file 
let g:SrcExpl_updateTagsCmd = "ctags --sort=foldcase -R ." 

" // Set "<F12>" key for updating the tags file artificially 
let g:SrcExpl_updateTagsKey = "<F12>" 
" }

" Plugin: taglist {
"map tl :silent! Tlist<CR> "do not need this, since we combine it into winmanager
let Tlist_Ctags_Cmd='ctags' 
let Tlist_Show_One_File=0
let Tlist_File_Fold_Auto_Close=1
let Tlist_Exit_OnlyWindow=1
let Tlist_Process_File_Always=0
let Tlist_Inc_Winwidth=0
"let Tlist_Use_Horiz_Window=1
"let Tlist_Use_Right_Window=1
"let Tlist_Auto_Open=0
"let Tlist_Close_On_Select=0
"let Tlist_Display_Tag_Scope=0
"let Tlist_Display_Prototype=1
"let Tlist_WinHeight=10
let Tlist_WinWidth=10
" }

" Plugin: Smart-Home {
nmap <silent> <Home> :SmartHomeKey <CR>
imap <silent> <Home> <C-O>:SmartHomeKey<CR>
" }

" Plugin: SingleCompile {
let common_run_command = './$(FILE_TITLE)$'
call SingleCompile#SetCompilerTemplate('c', 'gcc', 'GNU C Compiler',
                \'gcc', '-g -Wall -o $(FILE_TITLE)$', common_run_command)
call SingleCompile#SetCompilerTemplate('cpp', 'g++',
                \'GNU C++ Compiler', 'g++', '-g -Wall -o $(FILE_TITLE)$',
                \common_run_command)
nmap <F9> :SCCompile<cr>:cw<cr>
nmap <F8> :SCCompileRun<cr> 
" }

" Plugin: Buf Explorer {
map bf   :BufExplorer<CR>
" }

" Plugin: VIM-Latex {
let g:tex_flavor = 'xetex'
let g:Tex_FormatDependency_pdf = 'pdf'
let g:Tex_CompileRule_pdf = 'xelatex $*'
let g:Tex_DefaultTargetFormat = 'pdf'
let g:Tex_ViewRule_pdf = 'okular'
" }

" Plugin: Cpp11-Syntax-Support {
au BufNewFile,BufRead *.cpp set syntax=cpp11
au BufNewFile,BufRead *.hpp set syntax=cpp11
" }

" Plugin: vim-powerline {
set laststatus=2
" }

" Plugin: ctrlp {
let g:ctrlp_map = '<c-p>'
let g:ctrlp_cmd = 'CtrlPBuffer'
" }

" Plugin: neocomplcache {
" Disable AutoComplPop.
let g:acp_enableAtStartup = 0
" Use neocomplcache.
let g:neocomplcache_enable_at_startup = 1
" Use smartcase.
let g:neocomplcache_enable_smart_case = 1
" Use camel case completion.
let g:neocomplcache_enable_camel_case_completion = 1
" Use underbar completion.
let g:neocomplcache_enable_underbar_completion = 1
" Set minimum syntax keyword length.
let g:neocomplcache_min_syntax_length = 3
let g:neocomplcache_lock_buffer_name_pattern = '\*ku\*'

" Define dictionary.
let g:neocomplcache_dictionary_filetype_lists = {
    \ 'default' : '',
    \ 'vimshell' : $HOME.'/.vimshell_hist',
    \ 'scheme' : $HOME.'/.gosh_completions'
    \ }

" Define keyword.
if !exists('g:neocomplcache_keyword_patterns')
  let g:neocomplcache_keyword_patterns = {}
endif
let g:neocomplcache_keyword_patterns['default'] = '\h\w*'

" Plugin key-mappings.
imap <C-k>     <Plug>(neocomplcache_snippets_expand)
smap <C-k>     <Plug>(neocomplcache_snippets_expand)
inoremap <expr><C-g>     neocomplcache#undo_completion()
inoremap <expr><C-l>     neocomplcache#complete_common_string()

" SuperTab like snippets behavior.
"imap <expr><TAB> neocomplcache#sources#snippets_complete#expandable() ? "\<Plug>(neocomplcache_snippets_expand)" : pumvisible() ? "\<C-n>" : "\<TAB>"

" Recommended key-mappings.
" <CR>: close popup and save indent.
inoremap <expr><CR>  neocomplcache#smart_close_popup() . "\<CR>"
" <TAB>: completion.
inoremap <expr><TAB>  pumvisible() ? "\<C-n>" : "\<TAB>"
" <C-h>, <BS>: close popup and delete backword char.
inoremap <expr><C-h> neocomplcache#smart_close_popup()."\<C-h>"
inoremap <expr><BS> neocomplcache#smart_close_popup()."\<C-h>"
inoremap <expr><C-y>  neocomplcache#close_popup()
inoremap <expr><C-e>  neocomplcache#cancel_popup()

" AutoComplPop like behavior.
"let g:neocomplcache_enable_auto_select = 1

" Enable omni completion.
autocmd FileType css setlocal omnifunc=csscomplete#CompleteCSS
autocmd FileType html,markdown setlocal omnifunc=htmlcomplete#CompleteTags
autocmd FileType javascript setlocal omnifunc=javascriptcomplete#CompleteJS
autocmd FileType python setlocal omnifunc=pythoncomplete#Complete
autocmd FileType xml setlocal omnifunc=xmlcomplete#CompleteTags

" Enable heavy omni completion.
if !exists('g:neocomplcache_omni_patterns')
  let g:neocomplcache_omni_patterns = {}
endif
let g:neocomplcache_omni_patterns.ruby = '[^. *\t]\.\w*\|\h\w*::'
"autocmd FileType ruby setlocal omnifunc=rubycomplete#Complete
let g:neocomplcache_omni_patterns.php = '[^. \t]->\h\w*\|\h\w*::'
let g:neocomplcache_omni_patterns.c = '\%(\.\|->\)\h\w*'
let g:neocomplcache_omni_patterns.cpp = '\h\w*\%(\.\|->\)\h\w*\|\h\w*::'
" }

