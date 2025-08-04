
# Ukrainian Neovim keymap for Apple keyboard

New Apple MacBooks and probably other Apple keyboards have new and a bit different layout than 
other or older Apple keyboards. This includes changing positions of buttons like 
`` ` ``, `~`, `§`, `±` in English and `/`, `\`, `ґ`, `Ґ`, `₴` in Ukrainian.

This keymap allows to have all Ukrainian symbols as expected by (drawn on) the Apple keyboard layout.

Also, many Ukrainian keymaps for Neovim seem to be created from ~~russian~~ keymaps and use their naming of letters.
This keymap fixes this issue too.

And as a bonus, quickly typing `\\` (in Ukrainian layout) would insert an accent sign on the previous letter, like `а́`.


## Installation

### Plugin manager

This keymap can be installed with a plugin manager, like `Lazy`:
```lua
require('lazy').setup({
  -- ...
  'hrycko-mb/nvim-ukrainian-jcuken-mac-keymap'
  -- ...
})
```

Other plugin managers were not tested, but probably would also work.


### Manually

You can install this keymap manually, just by downloading the `keymap/ukrainian-jcuken-mac.vim`
and putting it in your configuration path (probably `~/.config/nvim`) as 
`/your/config/path/keymap/ukrainian-jcuken-mac.vim`.



## Usage

To activate the keymap add the following configuration to your lua config:
```lua
vim.o.keymap = 'ukrainian-jcuken-mac' -- sets the actual keymap
vim.o.spelllang = 'ua' -- sets spell checking language (requires spell file)
vim.cmd 'language uk_UA.UTF-8' -- sets Neovim language (useful when you don't have Ukrainian locale)
```


If you change languages quite often, editing config might be not ergonomic. 
For this you can set up command/keymaps to switch between languages. For example:
```lua
vim.api.nvim_create_user_command('UA', function()
  vim.o.keymap = 'ukrainian-jcuken-mac'
  vim.o.spelllang = 'ua'
  vim.cmd 'language uk_UA.UTF-8'
end, {})

vim.api.nvim_create_user_command('EN', function()
  vim.o.keymap = ''
  vim.o.spelllang = 'en_us'
  vim.cmd 'language en_US.UTF-8'
end, {})
```

This will create 2 commands `UA` and `EN` which will change the language correspondingly.

See documentation for more: \
<https://neovim.io/doc/user/usr_45.html#_language-for-messages> \
<https://neovim.io/doc/user/options.html#'keymap'>  \
<https://neovim.io/doc/user/options.html#'spelllang'>

