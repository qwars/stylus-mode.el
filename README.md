# stylus-mode.el

Emacs stylus-mode

```lisp
(add-to-list 'load-path "~/.emacs.d/modules/stylus-mode.el")
(require 'stylus-mode)
(add-hook 'stylus-mode-hook 
          (quote
           (lambda nil
             (setq-default ac-sources '(ac-source-abbrev ac-source-dictionary ac-source-words-in-same-mode-buffers))
             (auto-complete-mode 1)
             (make-local-variable 'ac-ignores)
             (add-to-list 'ac-ignores ";")
             (setq ac-modes (append ac-modes '(stylus-mode)))
             (ac-config-default)
             (setq-local whitespace-style
                         (quote
                          (face trailing tabs tab-mark)))
             (setq-local whitespace-display-mappings (quote ((tab-mark 9 [8594 9] [92 9]))))
             (whitespace-mode t)
             (set-face-foreground 'whitespace-tab "lightgray")
             (set-face-background 'whitespace-tab nil)
             (set-face-foreground 'whitespace-trailing "HotPink")
             (set-face-background 'whitespace-trailing "lightPink")
             (setq-local electric-pair-skip-whitespace-chars (quote (9 10)))
             (setq-local auto-indent-untabify-on-visit-file 'tabify)
             (setq-local auto-indent-backward-delete-char-behavior nil)
             (setq-local auto-indent-untabify-on-save-file 'tabify)
             (setq-local auto-indent-newline-function 'newline-and-indent)
             (setq-local adaptive-fill-regexp "[\t]*")
             )))
```
