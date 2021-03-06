# Spectator

_Test driven development red-green cycle for simple people!_

## The gist

Spectator is a simple watcher for your specs:
- it will execute a spec each time a file (spec or implementation) is modified or created (_really catches new files!_)
- it **does not** starts your whole suite at start, nor when a spec passes or fails (as autospec tends to do)
- _if you ask_ it runs the whole spec suite

> Started as a custom [Watchr](https://github.com/mynyml/watchr) script **Spectator** has grown up to a tiny gem!

### Compatibility

Works with RSpec-1 and RSpec-2 (looks for a `.rspec` file in the project root).


## Usage

Launch `spectator` in a terminal and go back to code!

The normal behavior is similar to `autotest --fast-start --no-full-after-failed` 
but gives the user a bit more control over execution. By hitting CTRL+C (or CMD+. on OSX)
you get the following prompt:

    ^C (Interrupted with CTRL+C)
    --- What to do now? (q=quit, a=all-specs): 

Type `q` and `ENTER` (or `CTRL+C` again) to quit.

Type `a` and `ENTER` (or `CTRL+C` again) to execute the whole suite of specs.


## Advanced (upcoming!)

If you want to override some path matching:

```ruby
spectate do
  case path
  when %r{lib/calibration_with_coefficients}
    specs.grep(%r{models/(logarithmic|polynomial)_calibration})
  when %r{app/models/telemetry_parameter}
    specs.grep(%r{models/telemetry_parameter})
  end
end
```



Copyright © 2011-2012 Elia Schito, released under the [MIT license](https://github.com/elia/spectator/blob/master/MIT-LICENSE)
