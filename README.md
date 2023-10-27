# photo-album

Lean Techniques showcase part deux

Hello!

This is ~~Ruby~~ bash script accomplishes the task for the LT Technical Showcases

## Setup

To run this solution ensure that you have jq installed on your machine. Type in jq on the Terminal

> jq

If this doesn't return output similar to this `jq - commandline JSON processor [version 1.7] ... <more output>` then you might not have jq installed on your system.

Here is the offical jq download/install instructions https://jqlang.github.io/jq/

Before executing the script you will need to give execution permissions to the file like so

```bash
chmod +x ./photo-album
```

This script was tested and ran with a zsh shell (the [default](https://support.apple.com/guide/terminal/change-the-default-shell-trml113/mac) for Apple machines)

## Running

Once you have jq setup and installed you can run the script like so from your terminal:

```bash
./photo-album <ALBUM ID ARGUMENT>
```

Where `<ALBUM ID ARGUMENT>` is an integer for an album id you wish to return

```bash
./photo-album help
```

Provides details for usage

### NOTES

- Giving no album id input will return all 5000 photos
- Giving an invalid album id with zero results returns a simple error message

## Testing

The tests are run as another bash script. You will need to chmod this file as well.

```bash
chmod +x ./tests
```

One test does rely on having a local server to serve up the json in the `/test_json` directory. Many methods exist to accomplish this.

A suggested method of accomplishing this is to run `python3 -m http.server` (https://docs.python.org/3/library/http.server.html) from the root directory of this project. Doing so allows for you to access the contents of the directory at `http://localhost:8000/test_json/single_photo.json`. This is for a "mocking" of sorts for test data.