# Web assembly test

## Abstract

*Testing web assembly*


## Usage

Due to some [security concerns](https://stackoverflow.com/questions/12001269/what-security-risks-exist-when-setting-access-control-allow-origin-to-accept-all), modern browsers don't allow running WebAssembly files directly from local directories. If you do try to run them this way, it'll result in [CORS](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing) or [MIME](https://en.wikipedia.org/wiki/MIME) errors.

Some sort of [HTTP server](https://en.wikipedia.org/wiki/HTTP_server) has to be set up. There are many possible options, but I'm using [PHP](https://www.php.net/) on [Windows 10](https://en.wikipedia.org/wiki/Windows_10):

1. Install PHP:
	1. Download PHP [here](https://www.php.net/downloads.php) (version 5.4 or later);
	1. Set Environment Path variable (restart not needed);
	1. Run `cmd.exe` and check success with `php -v`.
1. Run `cmd.exe` and navigate to the desired directory (`wastest` for this project);
1. Start the server by `php -S localhost:8000`;
	* *change `localhost` to a preferred `IP`, if needed*;
	* *change `8000` to a preferred port number, if needed*;
	* stop the server with `Ctrl+C` when done.
1. Open your favorite browser and go to `localhost:8000`.


## Development

General order: wat -> wabt -> wasm

**WebAssembly text format** (`.wat`) converted to **WebAssembly binary format** (`.wasm`) using [WebAssembly Binary Toolkit](https://github.com/webassembly/wabt).

For now, I'm using [an online demo](https://webassembly.github.io/wabt/demo/wat2wasm/). There is a button `Download` on upper-left panel for downloading the binary `.wasm` file.

Don't just copy-paste resulting binary data to a text file - it won't work (firstly, the magic number won't match).

You can check the binary with a binary/hex editor. I'm using a free open-sorce hex editor [Frhed](https://frhed.sourceforge.net/en/) (portable - doesn't need to be installed).


## Notes

Free to use and modify for whatever purposes. No copyrights apply.

*Work in progress, expect changes...*