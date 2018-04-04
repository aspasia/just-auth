# Just Auth - A simple and generic two factor authentication lib

[![Build Status](https://travis-ci.org/Commonfare-net/just-auth.svg?branch=master)](https://travis-ci.org/Commonfare-net/just-auth)
[![Clojars lib][clojars-logo]][clojars-url]
[![license][license-image]][license-url]

[clojars-url]: https://clojars.org/org.clojars.dyne/clj-storage
[clojars-logo]: https://clojars.org/images/clojars-logo.png
[license-url]: https://github.com/Commonfare-net/just-auth/blob/feature/start-without-email-config/LICENSE.txt
[license-image]: https://www.gnu.org/graphics/agplv3-155x51.png

This Clojure software is a simple two factor authentication library. It contains an `email` implementation and aims to be extended to more two factor implementations such as `sms`. It implements the main authentication functionalities like sign-up and sign-in as well as account activation, deactivation and password reset. Passwords and other sensitive information are encrypted and a bruteforce counter-attack mechanism is currently under development.For storage a mongo DB is used internally but an implementation of any other document DB could be added to the generic [storge lib](https://github.com/Commonfare-net/clj-storage) that has been used.

## How to use the library

### For production

You can create an email authenticator simply by calling 



#### Data encryption
For the data encryption the hash and checking functions can be passed as arguments 

` {:hash-fn clojure.lang.Fn
   :hash-check-fn clojure.lang.Fn} `

otherwise the default will be used xo

### Just to try out (no configuration needed)

### Run all tests

For the purpose we use Clojure's `midje` package, to be run with:

```
lein midje
```

### Run only the fast tests

Some of the tests are marked as slow. If you want to avoid running them you cn either

`lein midje :filter -slow`

or use the alias

`lein test-basic`

The just auth lib is Copyright (C) 2017 by the Dyne.org Foundation, Amsterdam

The development is lead by Aspasia Beneti <aspra@dyne.org>

## Acknowledgements

The Social Wallet API is Free and Open Source research and development
activity funded by the European Commission in the context of
the
[Collective Awareness Platforms for Sustainability and Social Innovation (CAPSSI)](https://ec.europa.eu/digital-single-market/en/collective-awareness) program. Social
Wallet API uses the
underlying [Freecoin-lib](https://github.com/dyne/freecoin-lib)
blockchain implementation library and adopted as a component of the
social wallet toolkit being developed for
the [Commonfare project](https://pieproject.eu) (grant nr. 687922) .


## License

Social Wallet API is Copyright (C) 2017 by the Dyne.org Foundation

This software and its documentation are designed, written and maintained
by Denis Roio <jaromil@dyne.org> and Aspasia Beneti <aspra@dyne.org>

```
This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
```