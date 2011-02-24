# Ruby-mode

This is a fork of `ruby-mode` from `ELPA` with some additions.

## Installation

Install it using `el-get`:

* Define macros for easy adding packages (thanks to Alexander Solovyov)

        (defmacro el-get-add (item)
          `(add-to-list 'el-get-sources ',item))

* Add package `ruby-mode`

        (el-get-add
         (:name ruby-mode
          :type git
          :url "git://github.com/little-arhat/ruby-mode.git"
          :features ruby-mode
          :after (lambda ()
                   (add-to-list 'auto-mode-alist '("\\.rb$" . ruby-mode))
                   (add-to-list 'interpreter-mode-alist '("ruby" . ruby-mode))
                   (add-to-list 'interpreter-mode-alist '("rbx" . ruby-mode))
                   (add-to-list 'interpreter-mode-alist '("jruby" . ruby-mode))
                   (add-to-list 'interpreter-mode-alist '("ruby1.9" . ruby-mode))
                   (add-to-list 'interpreter-mode-alist '("ruby1.8" . ruby-mode))

* That's all!

## Added features

* Shifting region left and right with (C-c <) and (C-c >).
