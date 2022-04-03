# twee-chapbook-mode

A major mode for Twee/Twine files written in the [Chapbook](https://klembot.github.io/chapbook/) story format.

`twee-chapbook-mode` should be combined with `twee-mode` for complete support of Chapbook files.

This project is now archived and no longer maintained.

## twee-mode features

- Display a menu to navigate to a passage header with Imenu
- Toggle the folding of a passage or all passages with `TAB` (like Org mode)
- Toggle narrowing on a passage with `C-x n`
- Move passages up or down with `outline-minor-mode`
- Jump to next or previous passage header with `outline-minor-mode`

For more details about `twee-mode`, refer to the [twee-mode repository](https://github.com/magoyette/twee-mode).

## twee-chapbook-mode features

- Syntax highlight for Chapbook
- Basic completion on Chapbook variables

## Configuration

`twee-mode` should be loaded just after `twee-chapbook-mode`.

``` emacs-lisp
(add-hook 'twee-chapbook-mode-hook 'twee-mode)
```

A sample use-package configuration for the two modes:

``` emacs-lisp
(use-package twee-chapbook-mode
  :mode (("\\.tw$" . twee-chapbook-mode)
         ("\\.twee$" . twee-chapbook-mode)))

(use-package twee-mode
  :after twee-chapbook-mode
  :init
  (add-hook 'twee-chapbook-mode-hook 'twee-mode)
  :config
  (define-key twee-mode-map (kbd "M-<up>") 'outline-move-subtree-up)
  (define-key twee-mode-map (kbd "M-<down>") 'outline-move-subtree-down)
  (define-key twee-mode-map (kbd "C-c C-f") 'outline-forward-same-level)
  (define-key twee-mode-map (kbd "C-c C-b") 'outline-backward-same-level))
```
