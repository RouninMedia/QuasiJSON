# QuasiJSON
**QuasiJSON** is an *escape* for JSON.

**QuasiJSON** replaces all the significant characters in JSON with *Unicode lookalikes*.

Consequently, **QuasiJSON** remains a `string` when parsed by:

 - `json_encode()` in **PHP**
 - `JSON.parse()` in **javascript** etc.
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
