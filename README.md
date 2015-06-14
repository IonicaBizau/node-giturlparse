<!---------------------------------------------------------------------------->
<!-- STOP, LOOK & LISTEN!                                                   -->
<!-- ====================                                                   -->
<!-- Do NOT edit this file directly since it's generated from a template    -->
<!-- file, using https://github.com/IonicaBizau/node-blah                   -->
<!--                                                                        -->
<!-- If you found a typo in documentation, fix it in the source files       -->
<!-- (`lib/*.js`) and make a pull request.                                  -->
<!--                                                                        -->
<!-- If you have any other ideas, open an issue.                            -->
<!--                                                                        -->
<!-- Please consider reading the contribution steps (CONTRIBUTING.md).      -->
<!-- * * * Thanks! * * *                                                    -->
<!---------------------------------------------------------------------------->

# git-url-parse [![Donate now][donate-now]][paypal-donations]

Parses and stringifies git urls.

## Installation

```sh
$ npm i git-url-parse
```

## Example

```js
// Dependencies
var GitUrlParse = require("git-url-parse");

// Constants
const urls = {
    ssh: "git@github.com:IonicaBizau/node-giturlparse.git"
  , https: "https://github.com/IonicaBizau/node-giturlparse.git"
  , local: "/opt/git/project.git"
  , file: "file:///opt/git/project.git"
};

// Parse
console.log(GitUrlParse(urls.ssh));
console.log(GitUrlParse(urls.https));
console.log(GitUrlParse(urls.local));
console.log(GitUrlParse(urls.file));

// Stringify
console.log(GitUrlParse(urls.ssh).toString("http"));
console.log(GitUrlParse(urls.ssh).toString("https"));
console.log(GitUrlParse(urls.https).toString("ssh"));

```

## Documentation

### `GitUrlParse(url)`
Parses a Git url.

#### Params
- **String** `url`: The Git url to parse.

#### Return
- **GitUrl** The `GitUrl` object containing:
 - `protocol` (String): The url protocol.
 - `source` (String): The Git provider (e.g. `"github.com"`).
 - `owner` (String): The repository owner.
 - `name` (String): The repository name.
 - `_` (String): The original url which was parsed.
 - `toString` (Function): A function to stringify the parsed url into another url type.

### `stringify(obj, type)`
Stringifies a `GitUrl` object.

#### Params
- **GitUrl** `obj`: The parsed Git url object.
- **String** `type`: The type of the stringified url (default `obj.protocol`).

#### Return
- **String** The stringified url.

## How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].

## License
[KINDLY][license] © [Ionică Bizău][website]–The [LICENSE](/LICENSE) file contains
a copy of the license.

[license]: http://ionicabizau.github.io/kindly-license/?author=Ionic%C4%83%20Biz%C4%83u%20%3Cbizauionica@gmail.com%3E&year=2015
[contributing]: /CONTRIBUTING.md
[website]: http://ionicabizau.net
[docs]: /DOCUMENTATION.md
[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=MG98D7NPFZ3MG
[donate-now]: http://i.imgur.com/jioicaN.png