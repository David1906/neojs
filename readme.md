<h1 align="center">
	<img width="360" src="./resources/neojs.png" alt="neojs">
	<br>
	<br>
</h1>

---

> Lightweight bag of utilities for NeoVim JavaScript developers

---

- A carefully crafted set of [plugins](./docs/plugins.md) for JavaScript development with [nvim][]
- [Sensible][] defaults and Syntax files for ES5 / ES6
- Awesome JS completion using [deoplete][] and [Tern][]
- Super fast asynchronous linting with [neomake][]
- Shortcut commands to interact with npm & node
- Ability to hit `Ctrl+R` to launch current file with node
- Wrappers to popular JavaScript task runners like [Grunt] or [Gulp]
- Same goodies for popular JavaScript test runners such as [Mocha] or [Ava]
- A good amount of [UltiSnips][] snippets for ES6 & React
- A bunch of templates (init new buffers with arbitrary content)

## Install

Install [vim-plug][] and put this line into your `.vimrc`

```
Plug 'mklabs/neojs'
```

On first launch, it will install the list of plugins defined in [docs/plugins.md](./docs/plugins.md).

Then, follow the following steps:

1. Run `:PlugStatus` to check your install and list of bundles
2. Run the `:UpdateRemotePlugins` command
3. Close vim and reopen again
4. Run `:Unite menu` or hit `<space><space>` to open the top Unite menu
5. Profit

## Plugins

The file `plugin/plugins.vim` uses vim-plug's API to dynamically load the plugins
listed in [docs/plugins.md](./docs/plugins.md)

When necessary, configuration for a given plugin can be found in
`plugin/<plugin>.vim` (ex. [plugin/neomake.vim](./plugin/neomake.vim)).

## Unite Menus

[Unite][] is an awesome plugin for advanced VIM users. It offers a rich API to
compose and design UI, in a simple way.

[oh-my-vim] and [joedicastro's
dotfiles](https://github.com/joedicastro/dotfiles/tree/master/vim) had the
briliant idea of using Unite to define a list of Menus with available commands
and mappings, which inspired the following:

- lint - Linter with neomake
- node - Node & npm menu
- task - Task helpers (Grunt & Gulp)
- tern - Tern commands (https://github.com/ternjs/tern_for_vim)
- test - Test helpers (Mocha & Ava)

**Ex.**
<img src="./resources/menus.gif" alt="Unite menus" style="max-width:100%;">

---

### Node

[vim-node][] already provides excellent support for node developement.

[plugin/node.vim](./plugin/node.vim) adds a few more goodies:

- `:NodeRun` command to open a vertical `:terminal` buffer with `node` command.
  The current buffer is executed and the result displayed.

- `Ctrl+R` is the default mapping to run `:NodeRun`

- `:Node <args>` opens a 2-lines horizontal buffer with node prompt

- `:Require <args>` helper to quickly add new require statements

### npm

- `:Npm <command> [options]` Wrapper on top of `npm`.

- `:Npmi packages...` alias for `:Npm install <args> --save`, except that it opens
  an horizontal buffer with only two lines displayed.

### Snippets

A list of [UltiSnips][] snippets can be found in the [snippets](./snippets)
directory.

- Common snippets like `f)`, `()()` to create IIFE, `#!` to expand node
  shebang, `ok` for `Object.keys()`, `e`, `l` to expand `console.`

- ES6 snippets from https://github.com/isRuslan/vim-es6/tree/master/UltiSnips

- React snippets from https://github.com/bentayloruk/vim-react-es6-snippets

Run `:UltiSnipsEdit` to edit them or add additional ones.

### Templates

[t.vim][] is a small "template" or scaffolding tool.

It takes a list of template files from `~/.vim/templates` and use them to
initialize new buffer from predefined content.

Mustache like placeholders can be used to quickly jump from one item to
another. With a little more work, [t.vim][] will ask the user for values to
quickly replace `{{ var }}`.

See [templates/](./templates) directory to see the list of available
templates.

You can add more templates in `~/.vim/templates`. The filename is important:
Use `<language>.<ext>` for a generic template to use for a particular filetype.
Any other name can be used for a more specific template. `package.json` is a
good example.


## Configuration

- `g:neojs_bundles` Path to vim-plug plugin directories (`~/.vim/bundles`)
- `g:neojs_unite_delimiter` Change the prefix value used in Unite Menus
- `g:neojs_pluginfile` Path to the file listing plugins to install and load
  (`~/.vim/bundles/neojs/docs/plugins.md`)

---

:heart:

[vim-plug]: https://github.com/junegunn/vim-plug
[Unite]: https://github.com/Shougo/unite.vim
[UltiSnips]: https://github.com/SirVer/ultisnips
[Neomake]: https://github.com/benekastah/neomake
[deoplete]: https://github.com/Shougo/deoplete.nvim
[Tern]: https://ternjs.net
[ternjs]: https://github.com/ternjs/tern_for_vim
[deoplete-ternjs]: https://github.com/carlitux/deoplete-ternjs
[vim-javascript]: https://github.com/pangloss/vim-javascript
[yajs.vim]: https://github.com/othree/yajs.vim
[es.next.syntax.vim]: https://github.com/othree/es.next.syntax.vim
[mdn.vim]: https://github.com/vimlab/mdn.vim
[jscs.vim]: https://github.com/vimlab/jscs.vim
[split-term.vim]: https://github.com/vimlab/split-term.vim
[vim-node]: https://github.com/moll/vim-node
[t.vim]: https://github.com/vimlab/t.vim
[node-host]: https://github.com/neovim/node-host
[Fugitive]: https://github.com/tpope/vim-fugitive
[neovim]: https://github.com/neovim/neovim
[nvim]: https://github.com/neovim/neovim
[ava]: https://github.com/sindresorhus/ava
[Mocha]: https://mochajs.org/
[Grunt]: http://gruntjs.com/
[Gulp]: http://gulpjs.com/
[vim-sensible]: https://github.com/tpope/vim-sensible
[Sensible]: https://github.com/tpope/vim-sensible
[oh-my-vim]: https://github.com/liangxianzhe/oh-my-vim
