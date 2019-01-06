# DISCLAIMER
BETA VERSION - UNDER TESTS

# MMM-FileDownloader

This is a module for the [MagicMirror²](https://github.com/MichMich/MagicMirror/).

This is a really simple module which could be used to download files (document, images, ...) from an URL and to store them on a local directory.

## Installation

In your terminal, go to your MagicMirror's Module folder:
````
cd ~/MagicMirror/modules
````

Clone this repository:
````
git clone https://github.com/schnibel/MMM-FileDownloader.git
````

Install dependencies: 
````
cd ~/MagicMirror/modules/MMM-FileDownloader
npm install
````


## Using the module

To use this module, add the following configuration block to the modules array in the `config/config.js` file:
```js
var config = {
    modules: [
        {
            module: 'MMM-FileDownloader',
            position: 'top_left',
            classes: 'myclass',   // if you want to use MMM-ProfileSwitcher
            config: {
                title: 'My title',
                localpath: "modules/MMM-FileDownloader/files/",
                max_parallel_download: 2,
                updateInterval: 60 * 60 * 1000,    // every hour
                show_table: true,

                files: [
                    // Files to download
                    {filename: "image1.jpg", url: "http://twitiq.com/wp-content/uploads/2017/05/sky.jpg"},
                    {
                      filename: "image2.jpg", 
                      url: "https://www.setaswall.com/wp-content/uploads/2017/03/Milky-Way-Stars-Space-Wallpaper-1920x1180.jpg"
                    },
                    {
                      filename: "image3.jpg", 
                      url: "https://images.wallpaperscraft.com/image/starry_sky_tree_milky_way_radiance_120245_7952x5304.jpg"},
                    {filename: "book.pdf", url:"https://www.debian.org/doc/manuals/debian-reference/debian-reference.en.pdf"},
               ]
            }
        },
    ]
}
```

## Configuration options

| Option                  | Description
|------------------------ |-----------
| `title`                 | *Optional* Title to be displayed <br><br>**Type:** `string`  <br>Default `File Downloader`
| `localpath`             | *Optional* Path where you want to store your downloaded files. The path shall exists and shall end with '/' <br><br>**Type:** `string`  <br>Default `modules/MMM-FileDownloader/files/`
| `max_parallel_download` | *Optional* Number of parallel download authorized to deal with performances <br><br>**Type:** `int` <br>Default `3` (parallel downloads)
| `updateInterval`        | *Optional* Time before downloading again the same files <br><br>**Type:** `int`(milliseconds) <br>Default `60 * 60 * 1000` milliseconds (1 hour)
| `show_table`            | *Optional* set to `true` if you want to see the module, and `false` if you want it runs in a transparent mode <br><br>**Type:** `boolean` <br>Default `true`

## Special Thanks
- [Michael Teeuw](https://github.com/MichMich) for creating the awesome [MagicMirror2](https://github.com/MichMich/MagicMirror/tree/develop) project that made this module possible.

