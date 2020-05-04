# The Amazing Power Of Pry

## Cool Features
* Tab completion
* Code inspection
* Debugger
* Syntax highlighting


## Configuring Pry
~/.pryrc
  * Customize and configure how Pry works
  * Shortcuts for debugger
  ```
  if defined?(PryByebug)
    Pry.commands.alias_command 'c', 'continue'
    Pry.commands.alias_command 's', 'step'
    Pry.commands.alias_command 'n', 'next'
    Pry.commands.alias_command 'f', 'finish'
  end
  ```

## Contexts
* `pry` starts a simple Pry REPL session
* `<object>.pry` starts a pry REPL with `<object>` as `self`
* `binding` context of variables, methods, etc available at the current line of code [Ruby Docs](https://ruby-doc.org/core-2.5.1/Binding.html)
  * `binding.pry` REPL started at the given point in the code

## List What's Available
* `ls <Object/Class>`
  * `-l` - local vars
  * `-i` - instance vars
  * `-q` - quiet (scope to this class)
  * `-v` - everything
  * `--grep`(or `-G`) - find
  * Shows vars and methods available on the given object

* `watch <expression>`
  * Adds an expression to watch and re-evaluate every time you hit enter
    *  If the output's value has changed, the new value will be printed to the console.

## How Did We Get Here?

* `whereami`
  * `-m` entire `m`ethod
  * `-c` entire `c`lass 
  * `-f` entire `f`ile
  * Shows the current location of the debugger with surrounding lines
    * Pass optional line count to show lines before/after

* `pry-backtrace`
  * backtrace showing how we got to this spot in pry

* `wtf` / `wtf!?!?!`
  * Last exception and backtrace (or extended backtrace)
  * `raise-up` 
    * Raises the last exception unless one provided
    * Useful if you want to force a certain exception

* `hist`
  * `-r` - replay line or range of lines
  * `-n` - no line numbers (copy/paste)

## Inspect The Code
* `show-source <method>` / `$`
  * Shows source and information about the method

* `show-source -d <method>` / `?` (`show-doc` - deprecated)
  * Shows documentation for the method
  * `gem-install pry-doc` needed for Ruby Core documentation

## Dig Into Rails
* `show-routes --grep`
* `find-route <controller/namespace>`
* `show-model`

## Learn More
* `help` / `help <cmd>`
  * Shows helpful documentation
  * Includes any defined aliases

