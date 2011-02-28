# Ruby-suite

This is a fork of `ruby-mode` and `inf-ruby` from `ELPA` with some additions.
Provide two modules as one package with some tweaks.

## Installation

Install it using `el-get`:

* Define macros for easy adding packages (thanks to Alexander Solovyov)

        (defmacro el-get-add (item)
          `(add-to-list 'el-get-sources ',item))

* Add package `ruby-mode`

        (el-get-add
         (:name ruby-suite
          :type git
          :url "git://github.com/little-arhat/ruby-suite.git"
          :features (ruby-mode inf-ruby)
          :after (lambda ()
                   (autoload 'inf-ruby "inf-ruby" "Run an inferior Ruby process" t)
                   (autoload 'inf-ruby-keys "inf-ruby" "" t)
                   (eval-after-load 'ruby-mode '(add-hook 'ruby-mode-hook 'inf-ruby-keys)))))

* That's all!

## Added features

* Shifting region left and right with `(C-c <)` and `(C-c >)`.

* `(C-c !)` starts ruby-interpreter in buffer.
