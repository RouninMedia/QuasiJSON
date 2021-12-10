# QuasiJSON
**QuasiJSON** is an *escape* for JSON.

**QuasiJSON** replaces all the significant characters in JSON with *Unicode lookalikes*.

Consequently, **QuasiJSON** *remains a `string`* when parsed by:

 - `json_encode()` in **PHP**
 - `JSON.parse()` in **javascript** etc.
_______

## Substitution table

Only six characters are replaced to transform **JSON** into **QuasiJSON**:

 - `{` becomes `｛` (Name: *Fullwidth Left Curly Bracket* | Unicode: `U+FF5B` | HTML: `&#65371;`)
 - `}` becomes `｝` (Name: *Fullwidth Right Curly Bracke* | Unicode: `U+FF5D` | HTML: `&#65373;`)
 - `[` becomes `［` (Name: *Fullwidth Left Square Bracket* | Unicode: `U+FF3B` | HTML: `&#65339;`)
 - `]` becomes `］` (Name: *Fullwidth Right Square Bracket* | Unicode: `U+FF3D` | HTML: `&#65341;`)
 - `"` becomes `¨` (Name: *Diaeresis* | Unicode: `U+00A8` | HTML: `&#168;`)
 - `:` becomes `：` (Name: *Small Colon* | Unicode: `U+FE55` | HTML: `&#65109;`)


_______

## Side-by-side comparison of JSON and QuasiJSON

### Example of JSON
```
{
	"alpha": true,
	"beta": "Test (2021-12-10 12:24)",
	"gamma": "Gamma Test",
	"delta": "0735773577357",
	"epsilon": "test@test.com",
	"zeta": ["Aleph", "Bet", "Vet", "Gimel"],
	"eta": 1639069696
}
```

### QuasiJSON equivalent
```
｛
	¨alpha¨： true,
	¨beta¨： ¨Test (2021-12-10 12:24)¨,
	¨gamma¨： ¨Gamma Test¨,
	¨delta¨： ¨0735773577357¨,
	¨epsilon¨： ¨test@test.com¨,
	¨zeta¨： ［¨Aleph¨, ¨Bet¨, ¨Vet¨, ¨Gimel¨］,
	¨eta¨： 1639069696
｝
```
_______

## PHP Functions

### `Convert_JSON_To_QuasiJSON()`

```
function Convert_JSON_To_QuasiJSON($myJSON) {

  $myQuasiJSON = $myJSON;
  $myQuasiJSON = str_replace('{', '｛', $myQuasiJSON);
  $myQuasiJSON = str_replace('}', '｝', $myQuasiJSON);
  $myQuasiJSON = str_replace('[', '［', $myQuasiJSON);
  $myQuasiJSON = str_replace(']', '］', $myQuasiJSON);
  $myQuasiJSON = str_replace('"', '¨', $myQuasiJSON);
  $myQuasiJSON = str_replace(':', '：', $myQuasiJSON);

  return $myQuasiJSON;
}
```

### `Convert_QuasiJSON_To_JSON()`

```
function Convert_QuasiJSON_To_JSON($myQuasiJSON) {

  $myJSON = $myQuasiJSON;
  $myJSON = str_replace('{', '｛', $myJSON);
  $myJSON = str_replace('}', '｝', $myJSON);
  $myJSON = str_replace('[', '［', $myJSON);
  $myJSON = str_replace(']', '］', $myJSON);
  $myJSON = str_replace('"', '¨', $myJSON);
  $myJSON = str_replace(':', '：', $myJSON);

  return $myJSON;
}
```
________

## Javascript Functions

### `convertJSONToQuasiJSON()`

```
const convertJSONToQuasiJSON = (myJSON) => {

  let quasiJSON = myJSON;
  
  quasiJSON = quasiJSON.replaceAll('{', '｛');
  quasiJSON = quasiJSON.replaceAll('}', '｝');
  quasiJSON = quasiJSON.replaceAll('[', '［');
  quasiJSON = quasiJSON.replaceAll(']', '］');
  quasiJSON = quasiJSON.replaceAll('"', '¨');
  quasiJSON = quasiJSON.replaceAll(':', '：');
  
  return quasiJSON;
}
```

### `convertQuasiJSONToJSON()`


```
const convertQuasiJSONToJSON = (myQuasiJSON) => {

  let myJSON = myQuasiJSON;
  
  myJSON = myJSON.replaceAll('{', '｛');
  myJSON = myJSON.replaceAll('}', '｝');
  myJSON = myJSON.replaceAll('[', '［');
  myJSON = myJSON.replaceAll(']', '］');
  myJSON = myJSON.replaceAll('"', '¨');
  myJSON = myJSON.replaceAll(':', '：');

  return myJSON;
}
```
