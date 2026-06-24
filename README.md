# umbraco

My [Umbraco](https://umbraco.com) local installation to demo [TinyMCE](https://www.tiny.cloud) with the official plugin or just to do some Umbraco tests and development.

Use at your own risks.

## How to use it

I use the following alias to get it started on my computer:

```shell
#
# umbraco
#
# Launch Umbraco locally
#
function umbraco() {
  echo "\n$fg[green]Let's start Umbraco$reset_color\n"

  cd /Users/fharper/Documents/code/tiugo/tiny/partners/umbraco/

  # Wait for the server then open URLs — runs in background
  (
    while ! nc -z localhost 44388; do
      sleep 0.5
    done
    echo "\n$fg[green]Opening the site at https://localhost:44388/$reset_color\n"
    echo "$fg[green]Opening the admin at https://localhost:44388/umbraco/$reset_color\n"
    open https://localhost:44388/
    open https://localhost:44388/umbraco/
  ) &

  dotnet run
}
```
