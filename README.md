# Wolfram Alpha CLI

This is a Bash script for using Wolfram Alpha in the command line. It allows you to get quick answers to a variety of queries and supports image output for certain types of queries.

## Prerequisites

Before running this tool, you must obtain an App ID from the Wolfram Alpha API. You can obtain an App ID by signing up for the [Wolfram Alpha API](https://products.wolframalpha.com/api/) and creating a new App ID.

## Requirements

Before using this script, you need to:

1. Set your Wolfram Alpha API key in the `WA_APPID` variable.
2. Configure the `VIEWER` variable. You can use a text-only API and a terminal that supports images or install [ImageMagick](https://imagemagick.org/index.php) to view images.
3. Optionally, configure the `BG` and `FG` variables depending on your preferred color scheme.

## Usage

1. Short answer mode: Queries the API for a short answer and displays it on the command line.
2. Full answer mode: If the API returns "No short answer available," downloads the full answer as an image and opens it in a viewer (by default, [kitty](https://sw.kovidgoyal.net/kitty/kitten/icat.html) with inline image viewing enabled).

### Short Answer

To query for a short answer, simply run the script with your query as an argument:

```bash
wa <query>
```

If a short answer is not available, the tool will download and display a full answer using the `$VIEWER` program.

### Full Answer

To download the full answer as an image and open it in the viewer, use the `-p` option:

```bash
wa -p <query>
```

By default, the viewer used is [kitty](https://sw.kovidgoyal.net/kitty/kitten/icat.html) with inline image viewing enabled. If you prefer a different viewer, you can change the VIEWER variable in the script.

For more examples of supported queries, refer to Wolfram Alpha's [examples page](https://www.wolframalpha.com/examples/).

## Comparison to original version

1. Improved error handling: Checks if the `WA_APPID` environment variable is set before making API calls, and prints an error message if it is not set.

2. Better user experience: Has an option (`-p`) to display images in a terminal using the `kitty` terminal emulator.

3. More readable code: Uses a more readable syntax for string interpolation, and has clearer variable names (`WA_APPID` instead of `APPID`)

## Credits

This script was originally written by Dmitry (http://dmi3.net) and can be found on [GitHub](https://github.com/dmi3/bin).
