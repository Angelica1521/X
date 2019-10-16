<!DOCTYPE HTML>
	<html lang="es">
		<head>
			<meta charset="UTF-8">
			<title >Choco ~ Art</title>
			<link rel="stylesheet" href="css/choco.css">
			<link rel="shortcut icon" type="image/vnd.microsoft.icon" href="css/img/z.ico">	
				 <script type="module">
     
						  const hilo = new Worker("choco.js"); 
						  vista.addEventListener("submit",Hilo);
						  boton.addEventListener("click",Http);
						  hilo.addEventListener("message", evt => muestraRespuesta(evt.data));

						  function muestraRespuesta(texto) {
							respuesta.value = texto;
						  }

						  function Hilo(evt) {
							evt.preventDefault();
							const modelo = leeModelo();
							hilo.postMessage(modelo);
						  }
						  function leeModelo() {
							return {
							  nom: nom.value.trim(),
							  area: area.value.trim()
							};
						  }

						  function Http() {
							const modelo = leeModelo();
						   
							fetch("nom=" + encodeURIComponent(modelo.nom)
							  + "&area=" + encodeURIComponent(modelo.area))
							 
							  .then(
							  
								respuestaHttp => {
							   
								  if (respuestaHttp.ok) {
								   
									return respuestaHttp.text();
								  } else {
								   
									throw new Error(respuestaHttp.statusText)
								  }
								})
							  .then(texto => muestraRespuesta(texto))
							  .catch(e => muestraRespuesta(e.message));
						  }
				</script>
		</head>
		<body>

			<header>
				<h1> Choco ~ Art</h1>
				<h4> El Arte de la Chocolateria</h4>
				<!--<h4 style="color:white;"><center>El Arte de la Chocolateria</center></h4> segunda forma-->
			</header>
				<br>
				<form class="ch" id="vista"><br>
				  <p><output id="respuesta"></output></p>
				 
					<h2 class="b"> ~ REGISTRO EMPLEADO ~</h2><br><br><hr class="x"></hr><br>
						<p class="a">NOMBRE:</p><input type="text" requires name="nombre" id="nom" placeholder="&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Nombre" size="20"><br><br>
						<p class="a">ÁREA:</p><input type="text" requires name="area" id="area" placeholder="&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Área" size="20" >
						
						<br><br><br><button type="submit" onclick="recibir()" class="boton">Hilos</button><br><br>	
						<button type="button" id="boton" class="boton">Http</button><br><br>
				</form><br><br>
				
				<footer class="etiqueta">Derechos reservado Choco ~ Art & copy@ ~ Pela Angélica Velázquez Nava ~ IC51-V</footer>
				
		</body>
	</html>
{
  "name": "functions",
  "description": "Cloud Functions for Firebase",
  "scripts": {
    "lint": "eslint .",
    "serve": "firebase serve --only functions",
    "shell": "firebase functions:shell",
    "start": "npm run shell",
    "deploy": "firebase deploy --only functions",
    "logs": "firebase functions:log"
  },
  "engines": {
    "node": "8"
  },
  "dependencies": {
    "firebase-admin": "^8.6.0",
    "firebase-functions": "^3.3.0"
  },
  "devDependencies": {
    "eslint": "^5.12.0",
    "eslint-plugin-promise": "^4.0.1",
    "firebase-functions-test": "^0.1.6"
  },
  "private": true
}

{
  "name": "functions",
  "requires": true,
  "lockfileVersion": 1,
  "dependencies": {
    "@babel/code-frame": {
      "version": "7.5.5",
      "resolved": "https://registry.npmjs.org/@babel/code-frame/-/code-frame-7.5.5.tgz",
      "integrity": "sha512-27d4lZoomVyo51VegxI20xZPuSHusqbQag/ztrBC7wegWoQ1nLREPVSKSW8byhTlzTKyNE4ifaTA6lCp7JjpFw==",
      "dev": true,
      "requires": {
        "@babel/highlight": "^7.0.0"
      }
    },
    "@babel/highlight": {
      "version": "7.5.0",
      "resolved": "https://registry.npmjs.org/@babel/highlight/-/highlight-7.5.0.tgz",
      "integrity": "sha512-7dV4eu9gBxoM0dAnj/BCFDW9LFU0zvTrkq0ugM7pnHEgguOEeOz1so2ZghEdzviYzQEED0r4EAgpsBChKy1TRQ==",
      "dev": true,
      "requires": {
        "chalk": "^2.0.0",
        "esutils": "^2.0.2",
        "js-tokens": "^4.0.0"
      }
    },
    "@firebase/app-types": {
      "version": "0.4.5",
      "resolved": "https://registry.npmjs.org/@firebase/app-types/-/app-types-0.4.5.tgz",
      "integrity": "sha512-r75NGsHMP2SZMIn43VRjuCLIU4+r5fR8azo7SlJ/vIbt8JBAIfZVnmLFl+Y9iyeYHV9nbRTy16goVyuwj7rPJg=="
    },
    "@firebase/database": {
      "version": "0.5.7",
      "resolved": "https://registry.npmjs.org/@firebase/database/-/database-0.5.7.tgz",
      "integrity": "sha512-zF0uVLXt4lSKxNMjQWoJ02oYIgb37BzX/reGl2SJ14Gq7BYVNvW/BniVZ6KGgA9MpH7e5kL0fDTFjZx5uS5kxg==",
      "requires": {
        "@firebase/database-types": "0.4.5",
        "@firebase/logger": "0.1.26",
        "@firebase/util": "0.2.29",
        "faye-websocket": "0.11.3",
        "tslib": "1.10.0"
      }
    },
    "@firebase/database-types": {
      "version": "0.4.5",
      "resolved": "https://registry.npmjs.org/@firebase/database-types/-/database-types-0.4.5.tgz",
      "integrity": "sha512-VtVtBJvmmN+rb3q6hewxiYMhRUOeAav87DVPkmEeFs0Q+SiinjEb/Po3e98LyRAX8nJDj0EsIUoiKuTy8IyQFw==",
      "requires": {
        "@firebase/app-types": "0.4.5"
      }
    },
    "@firebase/logger": {
      "version": "0.1.26",
      "resolved": "https://registry.npmjs.org/@firebase/logger/-/logger-0.1.26.tgz",
      "integrity": "sha512-0PDyG6lGobJThf7pD1LpLLpiL7T+zNzYz0EyonC4aisewSatTRZA42Ys8XZ2CG0Wydyi9A7ogkfYf0CTGKOU1g=="
    },
    "@firebase/util": {
      "version": "0.2.29",
      "resolved": "https://registry.npmjs.org/@firebase/util/-/util-0.2.29.tgz",
      "integrity": "sha512-nbCZ/9QnbmWukcOZTL0ccVBWYhiOwacf+Z2IhZIzesfXmjUbPTvLW+do95h+ejdpR7nNBLDoP7t7sz/8WVam+w==",
      "requires": {
        "tslib": "1.10.0"
      }
    },
    "@google-cloud/common": {
      "version": "2.2.2",
      "resolved": "https://registry.npmjs.org/@google-cloud/common/-/common-2.2.2.tgz",
      "integrity": "sha512-AgMdDgLeYlEG17tXtMCowE7mplm907pcugtfJYYAp06HNe9RDnunUIY5KMnn9yikYl7NXNofARC+hwG77Zsa4g==",
      "optional": true,
      "requires": {
        "@google-cloud/projectify": "^1.0.0",
        "@google-cloud/promisify": "^1.0.0",
        "arrify": "^2.0.0",
        "duplexify": "^3.6.0",
        "ent": "^2.2.0",
        "extend": "^3.0.2",
        "google-auth-library": "^5.0.0",
        "retry-request": "^4.0.0",
        "teeny-request": "^5.2.1"
      }
    },
    "@google-cloud/firestore": {
      "version": "2.4.0",
      "resolved": "https://registry.npmjs.org/@google-cloud/firestore/-/firestore-2.4.0.tgz",
      "integrity": "sha512-F6jXdfQAjfzY5svOJpCZeayQeCAdZ3mjpaDTCfv6YEaxfxxyGODHV8ZEuD6CHnY6jGPEdJz/1EOG3ENJhnWhmw==",
      "optional": true,
      "requires": {
        "bun": "^0.0.12",
        "deep-equal": "^1.0.1",
        "functional-red-black-tree": "^1.0.1",
        "google-gax": "^1.6.3",
        "through2": "^3.0.0"
      }
    },
    "@google-cloud/paginator": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/@google-cloud/paginator/-/paginator-2.0.1.tgz",
      "integrity": "sha512-HZ6UTGY/gHGNriD7OCikYWL/Eu0sTEur2qqse2w6OVsz+57se3nTkqH14JIPxtf0vlEJ8IJN5w3BdZ22pjCB8g==",
      "optional": true,
      "requires": {
        "arrify": "^2.0.0",
        "extend": "^3.0.2"
      }
    },
    "@google-cloud/projectify": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/@google-cloud/projectify/-/projectify-1.0.1.tgz",
      "integrity": "sha512-xknDOmsMgOYHksKc1GPbwDLsdej8aRNIA17SlSZgQdyrcC0lx0OGo4VZgYfwoEU1YS8oUxF9Y+6EzDOb0eB7Xg==",
      "optional": true
    },
    "@google-cloud/promisify": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/@google-cloud/promisify/-/promisify-1.0.2.tgz",
      "integrity": "sha512-7WfV4R/3YV5T30WRZW0lqmvZy9hE2/p9MvpI34WuKa2Wz62mLu5XplGTFEMK6uTbJCLWUxTcZ4J4IyClKucE5g==",
      "optional": true
    },
    "@google-cloud/storage": {
      "version": "3.3.1",
      "resolved": "https://registry.npmjs.org/@google-cloud/storage/-/storage-3.3.1.tgz",
      "integrity": "sha512-+OoVaJbETDh9cyDoRGe1MJE2Rhrd6JXjSP7GVpdxCUkwYw8pLll/Oz+84JEB82GebQlxG+GVHGcKYTVcSobB5g==",
      "optional": true,
      "requires": {
        "@google-cloud/common": "^2.1.1",
        "@google-cloud/paginator": "^2.0.0",
        "@google-cloud/promisify": "^1.0.0",
        "arrify": "^2.0.0",
        "compressible": "^2.0.12",
        "concat-stream": "^2.0.0",
        "date-and-time": "^0.10.0",
        "duplexify": "^3.5.0",
        "extend": "^3.0.2",
        "gaxios": "^2.0.1",
        "gcs-resumable-upload": "^2.2.4",
        "hash-stream-validation": "^0.2.1",
        "mime": "^2.2.0",
        "mime-types": "^2.0.8",
        "onetime": "^5.1.0",
        "p-limit": "^2.2.0",
        "pumpify": "^2.0.0",
        "readable-stream": "^3.4.0",
        "snakeize": "^0.1.0",
        "stream-events": "^1.0.1",
        "through2": "^3.0.0",
        "xdg-basedir": "^4.0.0"
      },
      "dependencies": {
        "readable-stream": {
          "version": "3.4.0",
          "resolved": "https://registry.npmjs.org/readable-stream/-/readable-stream-3.4.0.tgz",
          "integrity": "sha512-jItXPLmrSR8jmTRmRWJXCnGJsfy85mB3Wd/uINMXA65yrnFo0cPClFIUWzo2najVNSl+mx7/4W8ttlLWJe99pQ==",
          "optional": true,
          "requires": {
            "inherits": "^2.0.3",
            "string_decoder": "^1.1.1",
            "util-deprecate": "^1.0.1"
          }
        },
        "string_decoder": {
          "version": "1.3.0",
          "resolved": "https://registry.npmjs.org/string_decoder/-/string_decoder-1.3.0.tgz",
          "integrity": "sha512-hkRX8U1WjJFd8LsDJ2yQ/wWWxaopEsABU1XfkM8A+j0+85JAGppt16cr1Whg6KIbb4okU6Mql6BOj+uup/wKeA==",
          "optional": true,
          "requires": {
            "safe-buffer": "~5.2.0"
          }
        }
      }
    },
    "@grpc/grpc-js": {
      "version": "0.6.8",
      "resolved": "https://registry.npmjs.org/@grpc/grpc-js/-/grpc-js-0.6.8.tgz",
      "integrity": "sha512-/k038P6PBCwJVD/3Ndk3RlIIMWY/FNVRGF1vX8zXO0XXuM+1FJLHpJglKWxiZNF6jLpEZue9y0VpgnudMIk3zA==",
      "optional": true,
      "requires": {
        "semver": "^6.2.0"
      }
    },
    "@grpc/proto-loader": {
      "version": "0.5.2",
      "resolved": "https://registry.npmjs.org/@grpc/proto-loader/-/proto-loader-0.5.2.tgz",
      "integrity": "sha512-eBKD/FPxQoY1x6QONW2nBd54QUEyzcFP9FenujmoeDPy1rutVSHki1s/wR68F6O1QfCNDx+ayBH1O2CVNMzyyw==",
      "optional": true,
      "requires": {
        "lodash.camelcase": "^4.3.0",
        "protobufjs": "^6.8.6"
      }
    },
    "@protobufjs/aspromise": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/@protobufjs/aspromise/-/aspromise-1.1.2.tgz",
      "integrity": "sha1-m4sMxmPWaafY9vXQiToU00jzD78=",
      "optional": true
    },
    "@protobufjs/base64": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/@protobufjs/base64/-/base64-1.1.2.tgz",
      "integrity": "sha512-AZkcAA5vnN/v4PDqKyMR5lx7hZttPDgClv83E//FMNhR2TMcLUhfRUBHCmSl0oi9zMgDDqRUJkSxO3wm85+XLg==",
      "optional": true
    },
    "@protobufjs/codegen": {
      "version": "2.0.4",
      "resolved": "https://registry.npmjs.org/@protobufjs/codegen/-/codegen-2.0.4.tgz",
      "integrity": "sha512-YyFaikqM5sH0ziFZCN3xDC7zeGaB/d0IUb9CATugHWbd1FRFwWwt4ld4OYMPWu5a3Xe01mGAULCdqhMlPl29Jg==",
      "optional": true
    },
    "@protobufjs/eventemitter": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/@protobufjs/eventemitter/-/eventemitter-1.1.0.tgz",
      "integrity": "sha1-NVy8mLr61ZePntCV85diHx0Ga3A=",
      "optional": true
    },
    "@protobufjs/fetch": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/@protobufjs/fetch/-/fetch-1.1.0.tgz",
      "integrity": "sha1-upn7WYYUr2VwDBYZ/wbUVLDYTEU=",
      "optional": true,
      "requires": {
        "@protobufjs/aspromise": "^1.1.1",
        "@protobufjs/inquire": "^1.1.0"
      }
    },
    "@protobufjs/float": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/@protobufjs/float/-/float-1.0.2.tgz",
      "integrity": "sha1-Xp4avctz/Ap8uLKR33jIy9l7h9E=",
      "optional": true
    },
    "@protobufjs/inquire": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/@protobufjs/inquire/-/inquire-1.1.0.tgz",
      "integrity": "sha1-/yAOPnzyQp4tyvwRQIKOjMY48Ik=",
      "optional": true
    },
    "@protobufjs/path": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/@protobufjs/path/-/path-1.1.2.tgz",
      "integrity": "sha1-bMKyDFya1q0NzP0hynZz2Nf79o0=",
      "optional": true
    },
    "@protobufjs/pool": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/@protobufjs/pool/-/pool-1.1.0.tgz",
      "integrity": "sha1-Cf0V8tbTq/qbZbw2ZQbWrXhG/1Q=",
      "optional": true
    },
    "@protobufjs/utf8": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/@protobufjs/utf8/-/utf8-1.1.0.tgz",
      "integrity": "sha1-p3c2C1s5oaLlEG+OhY8v0tBgxXA=",
      "optional": true
    },
    "@types/body-parser": {
      "version": "1.17.1",
      "resolved": "https://registry.npmjs.org/@types/body-parser/-/body-parser-1.17.1.tgz",
      "integrity": "sha512-RoX2EZjMiFMjZh9lmYrwgoP9RTpAjSHiJxdp4oidAQVO02T7HER3xj9UKue5534ULWeqVEkujhWcyvUce+d68w==",
      "requires": {
        "@types/connect": "*",
        "@types/node": "*"
      }
    },
    "@types/connect": {
      "version": "3.4.32",
      "resolved": "https://registry.npmjs.org/@types/connect/-/connect-3.4.32.tgz",
      "integrity": "sha512-4r8qa0quOvh7lGD0pre62CAb1oni1OO6ecJLGCezTmhQ8Fz50Arx9RUszryR8KlgK6avuSXvviL6yWyViQABOg==",
      "requires": {
        "@types/node": "*"
      }
    },
    "@types/express": {
      "version": "4.17.1",
      "resolved": "https://registry.npmjs.org/@types/express/-/express-4.17.1.tgz",
      "integrity": "sha512-VfH/XCP0QbQk5B5puLqTLEeFgR8lfCJHZJKkInZ9mkYd+u8byX0kztXEQxEk4wZXJs8HI+7km2ALXjn4YKcX9w==",
      "requires": {
        "@types/body-parser": "*",
        "@types/express-serve-static-core": "*",
        "@types/serve-static": "*"
      }
    },
    "@types/express-serve-static-core": {
      "version": "4.16.9",
      "resolved": "https://registry.npmjs.org/@types/express-serve-static-core/-/express-serve-static-core-4.16.9.tgz",
      "integrity": "sha512-GqpaVWR0DM8FnRUJYKlWgyARoBUAVfRIeVDZQKOttLFp5SmhhF9YFIYeTPwMd/AXfxlP7xVO2dj1fGu0Q+krKQ==",
      "requires": {
        "@types/node": "*",
        "@types/range-parser": "*"
      }
    },
    "@types/lodash": {
      "version": "4.14.141",
      "resolved": "https://registry.npmjs.org/@types/lodash/-/lodash-4.14.141.tgz",
      "integrity": "sha512-v5NYIi9qEbFEUpCyikmnOYe4YlP8BMUdTcNCAquAKzu+FA7rZ1onj9x80mbnDdOW/K5bFf3Tv5kJplP33+gAbQ==",
      "dev": true
    },
    "@types/long": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/@types/long/-/long-4.0.0.tgz",
      "integrity": "sha512-1w52Nyx4Gq47uuu0EVcsHBxZFJgurQ+rTKS3qMHxR1GY2T8c2AJYd6vZoZ9q1rupaDjU0yT+Jc2XTyXkjeMA+Q==",
      "optional": true
    },
    "@types/mime": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/@types/mime/-/mime-2.0.1.tgz",
      "integrity": "sha512-FwI9gX75FgVBJ7ywgnq/P7tw+/o1GUbtP0KzbtusLigAOgIgNISRK0ZPl4qertvXSIE8YbsVJueQ90cDt9YYyw=="
    },
    "@types/node": {
      "version": "8.10.54",
      "resolved": "https://registry.npmjs.org/@types/node/-/node-8.10.54.tgz",
      "integrity": "sha512-kaYyLYf6ICn6/isAyD4K1MyWWd5Q3JgH6bnMN089LUx88+s4W8GvK9Q6JMBVu5vsFFp7pMdSxdKmlBXwH/VFRg=="
    },
    "@types/range-parser": {
      "version": "1.2.3",
      "resolved": "https://registry.npmjs.org/@types/range-parser/-/range-parser-1.2.3.tgz",
      "integrity": "sha512-ewFXqrQHlFsgc09MK5jP5iR7vumV/BYayNC6PgJO2LPe8vrnNFyjQjSppfEngITi0qvfKtzFvgKymGheFM9UOA=="
    },
    "@types/serve-static": {
      "version": "1.13.3",
      "resolved": "https://registry.npmjs.org/@types/serve-static/-/serve-static-1.13.3.tgz",
      "integrity": "sha512-oprSwp094zOglVrXdlo/4bAHtKTAxX6VT8FOZlBKrmyLbNvE1zxZyJ6yikMVtHIvwP45+ZQGJn+FdXGKTozq0g==",
      "requires": {
        "@types/express-serve-static-core": "*",
        "@types/mime": "*"
      }
    },
    "abort-controller": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/abort-controller/-/abort-controller-3.0.0.tgz",
      "integrity": "sha512-h8lQ8tacZYnR3vNQTgibj+tODHI5/+l06Au2Pcriv/Gmet0eaj4TwWH41sO9wnHDiQsEj19q0drzdWdeAHtweg==",
      "optional": true,
      "requires": {
        "event-target-shim": "^5.0.0"
      }
    },
    "accepts": {
      "version": "1.3.7",
      "resolved": "https://registry.npmjs.org/accepts/-/accepts-1.3.7.tgz",
      "integrity": "sha512-Il80Qs2WjYlJIBNzNkK6KYqlVMTbZLXgHx2oT0pU/fjRHyEp+PEfEPY0R3WCwAGVOtauxh1hOxNgIf5bv7dQpA==",
      "requires": {
        "mime-types": "~2.1.24",
        "negotiator": "0.6.2"
      }
    },
    "acorn": {
      "version": "6.3.0",
      "resolved": "https://registry.npmjs.org/acorn/-/acorn-6.3.0.tgz",
      "integrity": "sha512-/czfa8BwS88b9gWQVhc8eknunSA2DoJpJyTQkhheIf5E48u1N0R4q/YxxsAeqRrmK9TQ/uYfgLDfZo91UlANIA==",
      "dev": true
    },
    "acorn-jsx": {
      "version": "5.0.2",
      "resolved": "https://registry.npmjs.org/acorn-jsx/-/acorn-jsx-5.0.2.tgz",
      "integrity": "sha512-tiNTrP1MP0QrChmD2DdupCr6HWSFeKVw5d/dHTu4Y7rkAkRhU/Dt7dphAfIUyxtHpl/eBVip5uTNSpQJHylpAw==",
      "dev": true
    },
    "agent-base": {
      "version": "4.3.0",
      "resolved": "https://registry.npmjs.org/agent-base/-/agent-base-4.3.0.tgz",
      "integrity": "sha512-salcGninV0nPrwpGNn4VTXBb1SOuXQBiqbrNXoeizJsHrsL6ERFM2Ne3JUSBWRE6aeNJI2ROP/WEEIDUiDe3cg==",
      "optional": true,
      "requires": {
        "es6-promisify": "^5.0.0"
      }
    },
    "ajv": {
      "version": "6.10.2",
      "resolved": "https://registry.npmjs.org/ajv/-/ajv-6.10.2.tgz",
      "integrity": "sha512-TXtUUEYHuaTEbLZWIKUr5pmBuhDLy+8KYtPYdcV8qC+pOZL+NKqYwvWSRrVXHn+ZmRRAu8vJTAznH7Oag6RVRw==",
      "dev": true,
      "requires": {
        "fast-deep-equal": "^2.0.1",
        "fast-json-stable-stringify": "^2.0.0",
        "json-schema-traverse": "^0.4.1",
        "uri-js": "^4.2.2"
      }
    },
    "ansi-escapes": {
      "version": "3.2.0",
      "resolved": "https://registry.npmjs.org/ansi-escapes/-/ansi-escapes-3.2.0.tgz",
      "integrity": "sha512-cBhpre4ma+U0T1oM5fXg7Dy1Jw7zzwv7lt/GoCpr+hDQJoYnKVPLL4dCvSEFMmQurOQvSrwT7SL/DAlhBI97RQ==",
      "dev": true
    },
    "ansi-regex": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/ansi-regex/-/ansi-regex-3.0.0.tgz",
      "integrity": "sha1-7QMXwyIGT3lGbAKWa922Bas32Zg=",
      "dev": true
    },
    "ansi-styles": {
      "version": "3.2.1",
      "resolved": "https://registry.npmjs.org/ansi-styles/-/ansi-styles-3.2.1.tgz",
      "integrity": "sha512-VT0ZI6kZRdTh8YyJw3SMbYm/u+NqfsAxEpWO0Pf9sq8/e94WxxOpPKx9FR1FlyCtOVDNOQ+8ntlqFxiRc+r5qA==",
      "dev": true,
      "requires": {
        "color-convert": "^1.9.0"
      }
    },
    "argparse": {
      "version": "1.0.10",
      "resolved": "https://registry.npmjs.org/argparse/-/argparse-1.0.10.tgz",
      "integrity": "sha512-o5Roy6tNG4SL/FOkCAN6RzjiakZS25RLYFrcMttJqbdd8BWrnA+fGz57iN5Pb06pvBGvl5gQ0B48dJlslXvoTg==",
      "dev": true,
      "requires": {
        "sprintf-js": "~1.0.2"
      }
    },
    "array-flatten": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/array-flatten/-/array-flatten-1.1.1.tgz",
      "integrity": "sha1-ml9pkFGx5wczKPKgCJaLZOopVdI="
    },
    "arrify": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/arrify/-/arrify-2.0.1.tgz",
      "integrity": "sha512-3duEwti880xqi4eAMN8AyR4a0ByT90zoYdLlevfrvU43vb0YZwZVfxOgxWrLXXXpyugL0hNZc9G6BiB5B3nUug==",
      "optional": true
    },
    "astral-regex": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/astral-regex/-/astral-regex-1.0.0.tgz",
      "integrity": "sha512-+Ryf6g3BKoRc7jfp7ad8tM4TtMiaWvbF/1/sQcZPkkS7ag3D5nMBCe2UfOTONtAkaG0tO0ij3C5Lwmf1EiyjHg==",
      "dev": true
    },
    "balanced-match": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/balanced-match/-/balanced-match-1.0.0.tgz",
      "integrity": "sha1-ibTRmasr7kneFk6gK4nORi1xt2c=",
      "dev": true
    },
    "base64-js": {
      "version": "1.3.1",
      "resolved": "https://registry.npmjs.org/base64-js/-/base64-js-1.3.1.tgz",
      "integrity": "sha512-mLQ4i2QO1ytvGWFWmcngKO//JXAQueZvwEKtjgQFM4jIK0kU+ytMfplL8j+n5mspOfjHwoAg+9yhb7BwAHm36g==",
      "optional": true
    },
    "bignumber.js": {
      "version": "7.2.1",
      "resolved": "https://registry.npmjs.org/bignumber.js/-/bignumber.js-7.2.1.tgz",
      "integrity": "sha512-S4XzBk5sMB+Rcb/LNcpzXr57VRTxgAvaAEDAl1AwRx27j00hT84O6OkteE7u8UB3NuaaygCRrEpqox4uDOrbdQ==",
      "optional": true
    },
    "body-parser": {
      "version": "1.19.0",
      "resolved": "https://registry.npmjs.org/body-parser/-/body-parser-1.19.0.tgz",
      "integrity": "sha512-dhEPs72UPbDnAQJ9ZKMNTP6ptJaionhP5cBb541nXPlW60Jepo9RV/a4fX4XWW9CuFNK22krhrj1+rgzifNCsw==",
      "requires": {
        "bytes": "3.1.0",
        "content-type": "~1.0.4",
        "debug": "2.6.9",
        "depd": "~1.1.2",
        "http-errors": "1.7.2",
        "iconv-lite": "0.4.24",
        "on-finished": "~2.3.0",
        "qs": "6.7.0",
        "raw-body": "2.4.0",
        "type-is": "~1.6.17"
      },
      "dependencies": {
        "debug": {
          "version": "2.6.9",
          "resolved": "https://registry.npmjs.org/debug/-/debug-2.6.9.tgz",
          "integrity": "sha512-bC7ElrdJaJnPbAP+1EotYvqZsb3ecl5wi6Bfi6BJTUcNowp6cvspg0jXznRTKDjm/E7AdgFBVeAPVMNcKGsHMA==",
          "requires": {
            "ms": "2.0.0"
          }
        },
        "ms": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.0.0.tgz",
          "integrity": "sha1-VgiurfwAvmwpAd9fmGF4jeDVl8g="
        }
      }
    },
    "brace-expansion": {
      "version": "1.1.11",
      "resolved": "https://registry.npmjs.org/brace-expansion/-/brace-expansion-1.1.11.tgz",
      "integrity": "sha512-iCuPHDFgrHX7H2vEI/5xpz07zSHB00TpugqhmYtVmMO6518mCuRMoOYFldEBl0g187ufozdaHgWKcYFb61qGiA==",
      "dev": true,
      "requires": {
        "balanced-match": "^1.0.0",
        "concat-map": "0.0.1"
      }
    },
    "buffer-equal-constant-time": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/buffer-equal-constant-time/-/buffer-equal-constant-time-1.0.1.tgz",
      "integrity": "sha1-+OcRMvf/5uAaXJaXpMbz5I1cyBk="
    },
    "buffer-from": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/buffer-from/-/buffer-from-1.1.1.tgz",
      "integrity": "sha512-MQcXEUbCKtEo7bhqEs6560Hyd4XaovZlO/k9V3hjVUF/zwW7KBVdSK4gIt/bzwS9MbR5qob+F5jusZsb0YQK2A==",
      "optional": true
    },
    "bun": {
      "version": "0.0.12",
      "resolved": "https://registry.npmjs.org/bun/-/bun-0.0.12.tgz",
      "integrity": "sha512-Toms18J9DqnT+IfWkwxVTB2EaBprHvjlMWrTIsfX4xbu3ZBqVBwrERU0em1IgtRe04wT+wJxMlKHZok24hrcSQ==",
      "optional": true,
      "requires": {
        "readable-stream": "~1.0.32"
      }
    },
    "bytes": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/bytes/-/bytes-3.1.0.tgz",
      "integrity": "sha512-zauLjrfCG+xvoyaqLoV8bLVXXNGC4JqlxFCutSDWA6fJrTo2ZuvLYTqZ7aHBLZSMOopbzwv8f+wZcVzfVTI2Dg=="
    },
    "callsites": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/callsites/-/callsites-3.1.0.tgz",
      "integrity": "sha512-P8BjAsXvZS+VIDUI11hHCQEv74YT67YUi5JJFNWIqL235sBmjX4+qx9Muvls5ivyNENctx46xQLQ3aTuE7ssaQ==",
      "dev": true
    },
    "chalk": {
      "version": "2.4.2",
      "resolved": "https://registry.npmjs.org/chalk/-/chalk-2.4.2.tgz",
      "integrity": "sha512-Mti+f9lpJNcwF4tWV8/OrTTtF1gZi+f8FqlyAdouralcFWFQWF2+NgCHShjkCb+IFBLq9buZwE1xckQU4peSuQ==",
      "dev": true,
      "requires": {
        "ansi-styles": "^3.2.1",
        "escape-string-regexp": "^1.0.5",
        "supports-color": "^5.3.0"
      }
    },
    "chardet": {
      "version": "0.7.0",
      "resolved": "https://registry.npmjs.org/chardet/-/chardet-0.7.0.tgz",
      "integrity": "sha512-mT8iDcrh03qDGRRmoA2hmBJnxpllMR+0/0qlzjqZES6NdiWDcZkCNAk4rPFZ9Q85r27unkiNNg8ZOiwZXBHwcA==",
      "dev": true
    },
    "cli-cursor": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/cli-cursor/-/cli-cursor-2.1.0.tgz",
      "integrity": "sha1-s12sN2R5+sw+lHR9QdDQ9SOP/LU=",
      "dev": true,
      "requires": {
        "restore-cursor": "^2.0.0"
      }
    },
    "cli-width": {
      "version": "2.2.0",
      "resolved": "https://registry.npmjs.org/cli-width/-/cli-width-2.2.0.tgz",
      "integrity": "sha1-/xnt6Kml5XkyQUewwR8PvLq+1jk=",
      "dev": true
    },
    "color-convert": {
      "version": "1.9.3",
      "resolved": "https://registry.npmjs.org/color-convert/-/color-convert-1.9.3.tgz",
      "integrity": "sha512-QfAUtd+vFdAtFQcC8CCyYt1fYWxSqAiK2cSD6zDB8N3cpsEBAvRxp9zOGg6G/SHHJYAT88/az/IuDGALsNVbGg==",
      "dev": true,
      "requires": {
        "color-name": "1.1.3"
      }
    },
    "color-name": {
      "version": "1.1.3",
      "resolved": "https://registry.npmjs.org/color-name/-/color-name-1.1.3.tgz",
      "integrity": "sha1-p9BVi9icQveV3UIyj3QIMcpTvCU=",
      "dev": true
    },
    "compressible": {
      "version": "2.0.17",
      "resolved": "https://registry.npmjs.org/compressible/-/compressible-2.0.17.tgz",
      "integrity": "sha512-BGHeLCK1GV7j1bSmQQAi26X+GgWcTjLr/0tzSvMCl3LH1w1IJ4PFSPoV5316b30cneTziC+B1a+3OjoSUcQYmw==",
      "optional": true,
      "requires": {
        "mime-db": ">= 1.40.0 < 2"
      }
    },
    "concat-map": {
      "version": "0.0.1",
      "resolved": "https://registry.npmjs.org/concat-map/-/concat-map-0.0.1.tgz",
      "integrity": "sha1-2Klr13/Wjfd5OnMDajug1UBdR3s=",
      "dev": true
    },
    "concat-stream": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/concat-stream/-/concat-stream-2.0.0.tgz",
      "integrity": "sha512-MWufYdFw53ccGjCA+Ol7XJYpAlW6/prSMzuPOTRnJGcGzuhLn4Scrz7qf6o8bROZ514ltazcIFJZevcfbo0x7A==",
      "optional": true,
      "requires": {
        "buffer-from": "^1.0.0",
        "inherits": "^2.0.3",
        "readable-stream": "^3.0.2",
        "typedarray": "^0.0.6"
      },
      "dependencies": {
        "readable-stream": {
          "version": "3.4.0",
          "resolved": "https://registry.npmjs.org/readable-stream/-/readable-stream-3.4.0.tgz",
          "integrity": "sha512-jItXPLmrSR8jmTRmRWJXCnGJsfy85mB3Wd/uINMXA65yrnFo0cPClFIUWzo2najVNSl+mx7/4W8ttlLWJe99pQ==",
          "optional": true,
          "requires": {
            "inherits": "^2.0.3",
            "string_decoder": "^1.1.1",
            "util-deprecate": "^1.0.1"
          }
        },
        "string_decoder": {
          "version": "1.3.0",
          "resolved": "https://registry.npmjs.org/string_decoder/-/string_decoder-1.3.0.tgz",
          "integrity": "sha512-hkRX8U1WjJFd8LsDJ2yQ/wWWxaopEsABU1XfkM8A+j0+85JAGppt16cr1Whg6KIbb4okU6Mql6BOj+uup/wKeA==",
          "optional": true,
          "requires": {
            "safe-buffer": "~5.2.0"
          }
        }
      }
    },
    "configstore": {
      "version": "5.0.0",
      "resolved": "https://registry.npmjs.org/configstore/-/configstore-5.0.0.tgz",
      "integrity": "sha512-eE/hvMs7qw7DlcB5JPRnthmrITuHMmACUJAp89v6PT6iOqzoLS7HRWhBtuHMlhNHo2AhUSA/3Dh1bKNJHcublQ==",
      "optional": true,
      "requires": {
        "dot-prop": "^5.1.0",
        "graceful-fs": "^4.1.2",
        "make-dir": "^3.0.0",
        "unique-string": "^2.0.0",
        "write-file-atomic": "^3.0.0",
        "xdg-basedir": "^4.0.0"
      }
    },
    "content-disposition": {
      "version": "0.5.3",
      "resolved": "https://registry.npmjs.org/content-disposition/-/content-disposition-0.5.3.tgz",
      "integrity": "sha512-ExO0774ikEObIAEV9kDo50o+79VCUdEB6n6lzKgGwupcVeRlhrj3qGAfwq8G6uBJjkqLrhT0qEYFcWng8z1z0g==",
      "requires": {
        "safe-buffer": "5.1.2"
      },
      "dependencies": {
        "safe-buffer": {
          "version": "5.1.2",
          "resolved": "https://registry.npmjs.org/safe-buffer/-/safe-buffer-5.1.2.tgz",
          "integrity": "sha512-Gd2UZBJDkXlY7GbJxfsE8/nvKkUEU1G38c1siN6QP6a9PT9MmHB8GnpscSmMJSoF8LOIrt8ud/wPtojys4G6+g=="
        }
      }
    },
    "content-type": {
      "version": "1.0.4",
      "resolved": "https://registry.npmjs.org/content-type/-/content-type-1.0.4.tgz",
      "integrity": "sha512-hIP3EEPs8tB9AT1L+NUqtwOAps4mk2Zob89MWXMHjHWg9milF/j4osnnQLXBCBFBk/tvIG/tUc9mOUJiPBhPXA=="
    },
    "cookie": {
      "version": "0.4.0",
      "resolved": "https://registry.npmjs.org/cookie/-/cookie-0.4.0.tgz",
      "integrity": "sha512-+Hp8fLp57wnUSt0tY0tHEXh4voZRDnoIrZPqlo3DPiI4y9lwg/jqx+1Om94/W6ZaPDOUbnjOt/99w66zk+l1Xg=="
    },
    "cookie-signature": {
      "version": "1.0.6",
      "resolved": "https://registry.npmjs.org/cookie-signature/-/cookie-signature-1.0.6.tgz",
      "integrity": "sha1-4wOogrNCzD7oylE6eZmXNNqzriw="
    },
    "core-util-is": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/core-util-is/-/core-util-is-1.0.2.tgz",
      "integrity": "sha1-tf1UIgqivFq1eqtxQMlAdUUDwac=",
      "optional": true
    },
    "cors": {
      "version": "2.8.5",
      "resolved": "https://registry.npmjs.org/cors/-/cors-2.8.5.tgz",
      "integrity": "sha512-KIHbLJqu73RGr/hnbrO9uBeixNGuvSQjul/jdFvS/KFSIH1hWVd1ng7zOHx+YrEfInLG7q4n6GHQ9cDtxv/P6g==",
      "requires": {
        "object-assign": "^4",
        "vary": "^1"
      }
    },
    "cross-spawn": {
      "version": "6.0.5",
      "resolved": "https://registry.npmjs.org/cross-spawn/-/cross-spawn-6.0.5.tgz",
      "integrity": "sha512-eTVLrBSt7fjbDygz805pMnstIs2VTBNkRm0qxZd+M7A5XDdxVRWO5MxGBXZhjY4cqLYLdtrGqRf8mBPmzwSpWQ==",
      "dev": true,
      "requires": {
        "nice-try": "^1.0.4",
        "path-key": "^2.0.1",
        "semver": "^5.5.0",
        "shebang-command": "^1.2.0",
        "which": "^1.2.9"
      },
      "dependencies": {
        "semver": {
          "version": "5.7.1",
          "resolved": "https://registry.npmjs.org/semver/-/semver-5.7.1.tgz",
          "integrity": "sha512-sauaDf/PZdVgrLTNYHRtpXa1iRiKcaebiKQ1BJdpQlWH2lCvexQdX55snPFyK7QzpudqbCI0qXFfOasHdyNDGQ==",
          "dev": true
        }
      }
    },
    "crypto-random-string": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/crypto-random-string/-/crypto-random-string-2.0.0.tgz",
      "integrity": "sha512-v1plID3y9r/lPhviJ1wrXpLeyUIGAZ2SHNYTEapm7/8A9nLPoyvVp3RK/EPFqn5kEznyWgYZNsRtYYIWbuG8KA==",
      "optional": true
    },
    "date-and-time": {
      "version": "0.10.0",
      "resolved": "https://registry.npmjs.org/date-and-time/-/date-and-time-0.10.0.tgz",
      "integrity": "sha512-IbIzxtvK80JZOVsWF6+NOjunTaoFVYxkAQoyzmflJyuRCJAJebehy48mPiCAedcGp4P7/UO3QYRWa0fe6INftg==",
      "optional": true
    },
    "debug": {
      "version": "3.2.6",
      "resolved": "https://registry.npmjs.org/debug/-/debug-3.2.6.tgz",
      "integrity": "sha512-mel+jf7nrtEl5Pn1Qx46zARXKDpBbvzezse7p7LqINmdoIk8PYP5SySaxEmYv6TZ0JyEKA1hsCId6DIhgITtWQ==",
      "optional": true,
      "requires": {
        "ms": "^2.1.1"
      }
    },
    "deep-equal": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/deep-equal/-/deep-equal-1.1.0.tgz",
      "integrity": "sha512-ZbfWJq/wN1Z273o7mUSjILYqehAktR2NVoSrOukDkU9kg2v/Uv89yU4Cvz8seJeAmtN5oqiefKq8FPuXOboqLw==",
      "optional": true,
      "requires": {
        "is-arguments": "^1.0.4",
        "is-date-object": "^1.0.1",
        "is-regex": "^1.0.4",
        "object-is": "^1.0.1",
        "object-keys": "^1.1.1",
        "regexp.prototype.flags": "^1.2.0"
      }
    },
    "deep-is": {
      "version": "0.1.3",
      "resolved": "https://registry.npmjs.org/deep-is/-/deep-is-0.1.3.tgz",
      "integrity": "sha1-s2nW+128E+7PUk+RsHD+7cNXzzQ=",
      "dev": true
    },
    "define-properties": {
      "version": "1.1.3",
      "resolved": "https://registry.npmjs.org/define-properties/-/define-properties-1.1.3.tgz",
      "integrity": "sha512-3MqfYKj2lLzdMSf8ZIZE/V+Zuy+BgD6f164e8K2w7dgnpKArBDerGYpM46IYYcjnkdPNMjPk9A6VFB8+3SKlXQ==",
      "optional": true,
      "requires": {
        "object-keys": "^1.0.12"
      }
    },
    "depd": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/depd/-/depd-1.1.2.tgz",
      "integrity": "sha1-m81S4UwJd2PnSbJ0xDRu0uVgtak="
    },
    "destroy": {
      "version": "1.0.4",
      "resolved": "https://registry.npmjs.org/destroy/-/destroy-1.0.4.tgz",
      "integrity": "sha1-l4hXRCxEdJ5CBmE+N5RiBYJqvYA="
    },
    "dicer": {
      "version": "0.3.0",
      "resolved": "https://registry.npmjs.org/dicer/-/dicer-0.3.0.tgz",
      "integrity": "sha512-MdceRRWqltEG2dZqO769g27N/3PXfcKl04VhYnBlo2YhH7zPi88VebsjTKclaOyiuMaGU72hTfw3VkUitGcVCA==",
      "requires": {
        "streamsearch": "0.1.2"
      }
    },
    "doctrine": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/doctrine/-/doctrine-3.0.0.tgz",
      "integrity": "sha512-yS+Q5i3hBf7GBkd4KG8a7eBNNWNGLTaEwwYWUijIYM7zrlYDM0BFXHjjPWlWZ1Rg7UaddZeIDmi9jF3HmqiQ2w==",
      "dev": true,
      "requires": {
        "esutils": "^2.0.2"
      }
    },
    "dot-prop": {
      "version": "5.1.0",
      "resolved": "https://registry.npmjs.org/dot-prop/-/dot-prop-5.1.0.tgz",
      "integrity": "sha512-n1oC6NBF+KM9oVXtjmen4Yo7HyAVWV2UUl50dCYJdw2924K6dX9bf9TTTWaKtYlRn0FEtxG27KS80ayVLixxJA==",
      "optional": true,
      "requires": {
        "is-obj": "^2.0.0"
      }
    },
    "duplexify": {
      "version": "3.7.1",
      "resolved": "https://registry.npmjs.org/duplexify/-/duplexify-3.7.1.tgz",
      "integrity": "sha512-07z8uv2wMyS51kKhD1KsdXJg5WQ6t93RneqRxUHnskXVtlYYkLqM0gqStQZ3pj073g687jPCHrqNfCzawLYh5g==",
      "optional": true,
      "requires": {
        "end-of-stream": "^1.0.0",
        "inherits": "^2.0.1",
        "readable-stream": "^2.0.0",
        "stream-shift": "^1.0.0"
      },
      "dependencies": {
        "isarray": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/isarray/-/isarray-1.0.0.tgz",
          "integrity": "sha1-u5NdSFgsuhaMBoNJV6VKPgcSTxE=",
          "optional": true
        },
        "readable-stream": {
          "version": "2.3.6",
          "resolved": "https://registry.npmjs.org/readable-stream/-/readable-stream-2.3.6.tgz",
          "integrity": "sha512-tQtKA9WIAhBF3+VLAseyMqZeBjW0AHJoxOtYqSUZNJxauErmLbVm2FW1y+J/YA9dUrAC39ITejlZWhVIwawkKw==",
          "optional": true,
          "requires": {
            "core-util-is": "~1.0.0",
            "inherits": "~2.0.3",
            "isarray": "~1.0.0",
            "process-nextick-args": "~2.0.0",
            "safe-buffer": "~5.1.1",
            "string_decoder": "~1.1.1",
            "util-deprecate": "~1.0.1"
          }
        },
        "safe-buffer": {
          "version": "5.1.2",
          "resolved": "https://registry.npmjs.org/safe-buffer/-/safe-buffer-5.1.2.tgz",
          "integrity": "sha512-Gd2UZBJDkXlY7GbJxfsE8/nvKkUEU1G38c1siN6QP6a9PT9MmHB8GnpscSmMJSoF8LOIrt8ud/wPtojys4G6+g==",
          "optional": true
        },
        "string_decoder": {
          "version": "1.1.1",
          "resolved": "https://registry.npmjs.org/string_decoder/-/string_decoder-1.1.1.tgz",
          "integrity": "sha512-n/ShnvDi6FHbbVfviro+WojiFzv+s8MPMHBczVePfUpDJLwoLT0ht1l4YwBCbi8pJAveEEdnkHyPyTP/mzRfwg==",
          "optional": true,
          "requires": {
            "safe-buffer": "~5.1.0"
          }
        }
      }
    },
    "ecdsa-sig-formatter": {
      "version": "1.0.11",
      "resolved": "https://registry.npmjs.org/ecdsa-sig-formatter/-/ecdsa-sig-formatter-1.0.11.tgz",
      "integrity": "sha512-nagl3RYrbNv6kQkeJIpt6NJZy8twLB/2vtz6yN9Z4vRKHN4/QZJIEbqohALSgwKdnksuY3k5Addp5lg8sVoVcQ==",
      "requires": {
        "safe-buffer": "^5.0.1"
      }
    },
    "ee-first": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/ee-first/-/ee-first-1.1.1.tgz",
      "integrity": "sha1-WQxhFWsK4vTwJVcyoViyZrxWsh0="
    },
    "emoji-regex": {
      "version": "7.0.3",
      "resolved": "https://registry.npmjs.org/emoji-regex/-/emoji-regex-7.0.3.tgz",
      "integrity": "sha512-CwBLREIQ7LvYFB0WyRvwhq5N5qPhc6PMjD6bYggFlI5YyDgl+0vxq5VHbMOFqLg7hfWzmu8T5Z1QofhmTIhItA==",
      "dev": true
    },
    "encodeurl": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/encodeurl/-/encodeurl-1.0.2.tgz",
      "integrity": "sha1-rT/0yG7C0CkyL1oCw6mmBslbP1k="
    },
    "end-of-stream": {
      "version": "1.4.4",
      "resolved": "https://registry.npmjs.org/end-of-stream/-/end-of-stream-1.4.4.tgz",
      "integrity": "sha512-+uw1inIHVPQoaVuHzRyXd21icM+cnt4CzD5rW+NC1wjOUSTOs+Te7FOv7AhN7vS9x/oIyhLP5PR1H+phQAHu5Q==",
      "optional": true,
      "requires": {
        "once": "^1.4.0"
      }
    },
    "ent": {
      "version": "2.2.0",
      "resolved": "https://registry.npmjs.org/ent/-/ent-2.2.0.tgz",
      "integrity": "sha1-6WQhkyWiHQX0RGai9obtbOX13R0=",
      "optional": true
    },
    "es6-promise": {
      "version": "4.2.8",
      "resolved": "https://registry.npmjs.org/es6-promise/-/es6-promise-4.2.8.tgz",
      "integrity": "sha512-HJDGx5daxeIvxdBxvG2cb9g4tEvwIk3i8+nhX0yGrYmZUzbkdg8QbDevheDB8gd0//uPj4c1EQua8Q+MViT0/w==",
      "optional": true
    },
    "es6-promisify": {
      "version": "5.0.0",
      "resolved": "https://registry.npmjs.org/es6-promisify/-/es6-promisify-5.0.0.tgz",
      "integrity": "sha1-UQnWLz5W6pZ8S2NQWu8IKRyKUgM=",
      "optional": true,
      "requires": {
        "es6-promise": "^4.0.3"
      }
    },
    "escape-html": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/escape-html/-/escape-html-1.0.3.tgz",
      "integrity": "sha1-Aljq5NPQwJdN4cFpGI7wBR0dGYg="
    },
    "escape-string-regexp": {
      "version": "1.0.5",
      "resolved": "https://registry.npmjs.org/escape-string-regexp/-/escape-string-regexp-1.0.5.tgz",
      "integrity": "sha1-G2HAViGQqN/2rjuyzwIAyhMLhtQ=",
      "dev": true
    },
    "eslint": {
      "version": "5.16.0",
      "resolved": "https://registry.npmjs.org/eslint/-/eslint-5.16.0.tgz",
      "integrity": "sha512-S3Rz11i7c8AA5JPv7xAH+dOyq/Cu/VXHiHXBPOU1k/JAM5dXqQPt3qcrhpHSorXmrpu2g0gkIBVXAqCpzfoZIg==",
      "dev": true,
      "requires": {
        "@babel/code-frame": "^7.0.0",
        "ajv": "^6.9.1",
        "chalk": "^2.1.0",
        "cross-spawn": "^6.0.5",
        "debug": "^4.0.1",
        "doctrine": "^3.0.0",
        "eslint-scope": "^4.0.3",
        "eslint-utils": "^1.3.1",
        "eslint-visitor-keys": "^1.0.0",
        "espree": "^5.0.1",
        "esquery": "^1.0.1",
        "esutils": "^2.0.2",
        "file-entry-cache": "^5.0.1",
        "functional-red-black-tree": "^1.0.1",
        "glob": "^7.1.2",
        "globals": "^11.7.0",
        "ignore": "^4.0.6",
        "import-fresh": "^3.0.0",
        "imurmurhash": "^0.1.4",
        "inquirer": "^6.2.2",
        "js-yaml": "^3.13.0",
        "json-stable-stringify-without-jsonify": "^1.0.1",
        "levn": "^0.3.0",
        "lodash": "^4.17.11",
        "minimatch": "^3.0.4",
        "mkdirp": "^0.5.1",
        "natural-compare": "^1.4.0",
        "optionator": "^0.8.2",
        "path-is-inside": "^1.0.2",
        "progress": "^2.0.0",
        "regexpp": "^2.0.1",
        "semver": "^5.5.1",
        "strip-ansi": "^4.0.0",
        "strip-json-comments": "^2.0.1",
        "table": "^5.2.3",
        "text-table": "^0.2.0"
      },
      "dependencies": {
        "debug": {
          "version": "4.1.1",
          "resolved": "https://registry.npmjs.org/debug/-/debug-4.1.1.tgz",
          "integrity": "sha512-pYAIzeRo8J6KPEaJ0VWOh5Pzkbw/RetuzehGM7QRRX5he4fPHx2rdKMB256ehJCkX+XRQm16eZLqLNS8RSZXZw==",
          "dev": true,
          "requires": {
            "ms": "^2.1.1"
          }
        },
        "semver": {
          "version": "5.7.1",
          "resolved": "https://registry.npmjs.org/semver/-/semver-5.7.1.tgz",
          "integrity": "sha512-sauaDf/PZdVgrLTNYHRtpXa1iRiKcaebiKQ1BJdpQlWH2lCvexQdX55snPFyK7QzpudqbCI0qXFfOasHdyNDGQ==",
          "dev": true
        }
      }
    },
    "eslint-plugin-promise": {
      "version": "4.2.1",
      "resolved": "https://registry.npmjs.org/eslint-plugin-promise/-/eslint-plugin-promise-4.2.1.tgz",
      "integrity": "sha512-VoM09vT7bfA7D+upt+FjeBO5eHIJQBUWki1aPvB+vbNiHS3+oGIJGIeyBtKQTME6UPXXy3vV07OL1tHd3ANuDw==",
      "dev": true
    },
    "eslint-scope": {
      "version": "4.0.3",
      "resolved": "https://registry.npmjs.org/eslint-scope/-/eslint-scope-4.0.3.tgz",
      "integrity": "sha512-p7VutNr1O/QrxysMo3E45FjYDTeXBy0iTltPFNSqKAIfjDSXC+4dj+qfyuD8bfAXrW/y6lW3O76VaYNPKfpKrg==",
      "dev": true,
      "requires": {
        "esrecurse": "^4.1.0",
        "estraverse": "^4.1.1"
      }
    },
    "eslint-utils": {
      "version": "1.4.2",
      "resolved": "https://registry.npmjs.org/eslint-utils/-/eslint-utils-1.4.2.tgz",
      "integrity": "sha512-eAZS2sEUMlIeCjBeubdj45dmBHQwPHWyBcT1VSYB7o9x9WRRqKxyUoiXlRjyAwzN7YEzHJlYg0NmzDRWx6GP4Q==",
      "dev": true,
      "requires": {
        "eslint-visitor-keys": "^1.0.0"
      }
    },
    "eslint-visitor-keys": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/eslint-visitor-keys/-/eslint-visitor-keys-1.1.0.tgz",
      "integrity": "sha512-8y9YjtM1JBJU/A9Kc+SbaOV4y29sSWckBwMHa+FGtVj5gN/sbnKDf6xJUl+8g7FAij9LVaP8C24DUiH/f/2Z9A==",
      "dev": true
    },
    "espree": {
      "version": "5.0.1",
      "resolved": "https://registry.npmjs.org/espree/-/espree-5.0.1.tgz",
      "integrity": "sha512-qWAZcWh4XE/RwzLJejfcofscgMc9CamR6Tn1+XRXNzrvUSSbiAjGOI/fggztjIi7y9VLPqnICMIPiGyr8JaZ0A==",
      "dev": true,
      "requires": {
        "acorn": "^6.0.7",
        "acorn-jsx": "^5.0.0",
        "eslint-visitor-keys": "^1.0.0"
      }
    },
    "esprima": {
      "version": "4.0.1",
      "resolved": "https://registry.npmjs.org/esprima/-/esprima-4.0.1.tgz",
      "integrity": "sha512-eGuFFw7Upda+g4p+QHvnW0RyTX/SVeJBDM/gCtMARO0cLuT2HcEKnTPvhjV6aGeqrCB/sbNop0Kszm0jsaWU4A==",
      "dev": true
    },
    "esquery": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/esquery/-/esquery-1.0.1.tgz",
      "integrity": "sha512-SmiyZ5zIWH9VM+SRUReLS5Q8a7GxtRdxEBVZpm98rJM7Sb+A9DVCndXfkeFUd3byderg+EbDkfnevfCwynWaNA==",
      "dev": true,
      "requires": {
        "estraverse": "^4.0.0"
      }
    },
    "esrecurse": {
      "version": "4.2.1",
      "resolved": "https://registry.npmjs.org/esrecurse/-/esrecurse-4.2.1.tgz",
      "integrity": "sha512-64RBB++fIOAXPw3P9cy89qfMlvZEXZkqqJkjqqXIvzP5ezRZjW+lPWjw35UX/3EhUPFYbg5ER4JYgDw4007/DQ==",
      "dev": true,
      "requires": {
        "estraverse": "^4.1.0"
      }
    },
    "estraverse": {
      "version": "4.3.0",
      "resolved": "https://registry.npmjs.org/estraverse/-/estraverse-4.3.0.tgz",
      "integrity": "sha512-39nnKffWz8xN1BU/2c79n9nB9HDzo0niYUqx6xyqUnyoAnQyyWpOTdZEeiCch8BBu515t4wp9ZmgVfVhn9EBpw==",
      "dev": true
    },
    "esutils": {
      "version": "2.0.3",
      "resolved": "https://registry.npmjs.org/esutils/-/esutils-2.0.3.tgz",
      "integrity": "sha512-kVscqXk4OCp68SZ0dkgEKVi6/8ij300KBWTJq32P/dYeWTSwK41WyTxalN1eRmA5Z9UU/LX9D7FWSmV9SAYx6g==",
      "dev": true
    },
    "etag": {
      "version": "1.8.1",
      "resolved": "https://registry.npmjs.org/etag/-/etag-1.8.1.tgz",
      "integrity": "sha1-Qa4u62XvpiJorr/qg6x9eSmbCIc="
    },
    "event-target-shim": {
      "version": "5.0.1",
      "resolved": "https://registry.npmjs.org/event-target-shim/-/event-target-shim-5.0.1.tgz",
      "integrity": "sha512-i/2XbnSz/uxRCU6+NdVJgKWDTM427+MqYbkQzD321DuCQJUqOuJKIA0IM2+W2xtYHdKOmZ4dR6fExsd4SXL+WQ==",
      "optional": true
    },
    "express": {
      "version": "4.17.1",
      "resolved": "https://registry.npmjs.org/express/-/express-4.17.1.tgz",
      "integrity": "sha512-mHJ9O79RqluphRrcw2X/GTh3k9tVv8YcoyY4Kkh4WDMUYKRZUq0h1o0w2rrrxBqM7VoeUVqgb27xlEMXTnYt4g==",
      "requires": {
        "accepts": "~1.3.7",
        "array-flatten": "1.1.1",
        "body-parser": "1.19.0",
        "content-disposition": "0.5.3",
        "content-type": "~1.0.4",
        "cookie": "0.4.0",
        "cookie-signature": "1.0.6",
        "debug": "2.6.9",
        "depd": "~1.1.2",
        "encodeurl": "~1.0.2",
        "escape-html": "~1.0.3",
        "etag": "~1.8.1",
        "finalhandler": "~1.1.2",
        "fresh": "0.5.2",
        "merge-descriptors": "1.0.1",
        "methods": "~1.1.2",
        "on-finished": "~2.3.0",
        "parseurl": "~1.3.3",
        "path-to-regexp": "0.1.7",
        "proxy-addr": "~2.0.5",
        "qs": "6.7.0",
        "range-parser": "~1.2.1",
        "safe-buffer": "5.1.2",
        "send": "0.17.1",
        "serve-static": "1.14.1",
        "setprototypeof": "1.1.1",
        "statuses": "~1.5.0",
        "type-is": "~1.6.18",
        "utils-merge": "1.0.1",
        "vary": "~1.1.2"
      },
      "dependencies": {
        "debug": {
          "version": "2.6.9",
          "resolved": "https://registry.npmjs.org/debug/-/debug-2.6.9.tgz",
          "integrity": "sha512-bC7ElrdJaJnPbAP+1EotYvqZsb3ecl5wi6Bfi6BJTUcNowp6cvspg0jXznRTKDjm/E7AdgFBVeAPVMNcKGsHMA==",
          "requires": {
            "ms": "2.0.0"
          }
        },
        "ms": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.0.0.tgz",
          "integrity": "sha1-VgiurfwAvmwpAd9fmGF4jeDVl8g="
        },
        "safe-buffer": {
          "version": "5.1.2",
          "resolved": "https://registry.npmjs.org/safe-buffer/-/safe-buffer-5.1.2.tgz",
          "integrity": "sha512-Gd2UZBJDkXlY7GbJxfsE8/nvKkUEU1G38c1siN6QP6a9PT9MmHB8GnpscSmMJSoF8LOIrt8ud/wPtojys4G6+g=="
        }
      }
    },
    "extend": {
      "version": "3.0.2",
      "resolved": "https://registry.npmjs.org/extend/-/extend-3.0.2.tgz",
      "integrity": "sha512-fjquC59cD7CyW6urNXK0FBufkZcoiGG80wTuPujX590cB5Ttln20E2UB4S/WARVqhXffZl2LNgS+gQdPIIim/g==",
      "optional": true
    },
    "external-editor": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/external-editor/-/external-editor-3.1.0.tgz",
      "integrity": "sha512-hMQ4CX1p1izmuLYyZqLMO/qGNw10wSv9QDCPfzXfyFrOaCSSoRfqE1Kf1s5an66J5JZC62NewG+mK49jOCtQew==",
      "dev": true,
      "requires": {
        "chardet": "^0.7.0",
        "iconv-lite": "^0.4.24",
        "tmp": "^0.0.33"
      }
    },
    "fast-deep-equal": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/fast-deep-equal/-/fast-deep-equal-2.0.1.tgz",
      "integrity": "sha1-ewUhjd+WZ79/Nwv3/bLLFf3Qqkk=",
      "dev": true
    },
    "fast-json-stable-stringify": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/fast-json-stable-stringify/-/fast-json-stable-stringify-2.0.0.tgz",
      "integrity": "sha1-1RQsDK7msRifh9OnYREGT4bIu/I=",
      "dev": true
    },
    "fast-levenshtein": {
      "version": "2.0.6",
      "resolved": "https://registry.npmjs.org/fast-levenshtein/-/fast-levenshtein-2.0.6.tgz",
      "integrity": "sha1-PYpcZog6FqMMqGQ+hR8Zuqd5eRc=",
      "dev": true
    },
    "fast-text-encoding": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/fast-text-encoding/-/fast-text-encoding-1.0.0.tgz",
      "integrity": "sha512-R9bHCvweUxxwkDwhjav5vxpFvdPGlVngtqmx4pIZfSUhM/Q4NiIUHB456BAf+Q1Nwu3HEZYONtu+Rya+af4jiQ==",
      "optional": true
    },
    "faye-websocket": {
      "version": "0.11.3",
      "resolved": "https://registry.npmjs.org/faye-websocket/-/faye-websocket-0.11.3.tgz",
      "integrity": "sha512-D2y4bovYpzziGgbHYtGCMjlJM36vAl/y+xUyn1C+FVx8szd1E+86KwVw6XvYSzOP8iMpm1X0I4xJD+QtUb36OA==",
      "requires": {
        "websocket-driver": ">=0.5.1"
      }
    },
    "figures": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/figures/-/figures-2.0.0.tgz",
      "integrity": "sha1-OrGi0qYsi/tDGgyUy3l6L84nyWI=",
      "dev": true,
      "requires": {
        "escape-string-regexp": "^1.0.5"
      }
    },
    "file-entry-cache": {
      "version": "5.0.1",
      "resolved": "https://registry.npmjs.org/file-entry-cache/-/file-entry-cache-5.0.1.tgz",
      "integrity": "sha512-bCg29ictuBaKUwwArK4ouCaqDgLZcysCFLmM/Yn/FDoqndh/9vNuQfXRDvTuXKLxfD/JtZQGKFT8MGcJBK644g==",
      "dev": true,
      "requires": {
        "flat-cache": "^2.0.1"
      }
    },
    "finalhandler": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/finalhandler/-/finalhandler-1.1.2.tgz",
      "integrity": "sha512-aAWcW57uxVNrQZqFXjITpW3sIUQmHGG3qSb9mUah9MgMC4NeWhNOlNjXEYq3HjRAvL6arUviZGGJsBg6z0zsWA==",
      "requires": {
        "debug": "2.6.9",
        "encodeurl": "~1.0.2",
        "escape-html": "~1.0.3",
        "on-finished": "~2.3.0",
        "parseurl": "~1.3.3",
        "statuses": "~1.5.0",
        "unpipe": "~1.0.0"
      },
      "dependencies": {
        "debug": {
          "version": "2.6.9",
          "resolved": "https://registry.npmjs.org/debug/-/debug-2.6.9.tgz",
          "integrity": "sha512-bC7ElrdJaJnPbAP+1EotYvqZsb3ecl5wi6Bfi6BJTUcNowp6cvspg0jXznRTKDjm/E7AdgFBVeAPVMNcKGsHMA==",
          "requires": {
            "ms": "2.0.0"
          }
        },
        "ms": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.0.0.tgz",
          "integrity": "sha1-VgiurfwAvmwpAd9fmGF4jeDVl8g="
        }
      }
    },
    "firebase-admin": {
      "version": "8.6.0",
      "resolved": "https://registry.npmjs.org/firebase-admin/-/firebase-admin-8.6.0.tgz",
      "integrity": "sha512-+JqOinU5bYUkg434LqEBXrHMrIBhL/+HwWEgbZpS1sBKHQRJK7LlcBrayqxvQKwJzgh5xs/JTInTmkozXk7h1w==",
      "requires": {
        "@firebase/database": "^0.5.1",
        "@google-cloud/firestore": "^2.0.0",
        "@google-cloud/storage": "^3.0.2",
        "@types/node": "^8.0.53",
        "dicer": "^0.3.0",
        "jsonwebtoken": "8.1.0",
        "node-forge": "0.7.4"
      }
    },
    "firebase-functions": {
      "version": "3.3.0",
      "resolved": "https://registry.npmjs.org/firebase-functions/-/firebase-functions-3.3.0.tgz",
      "integrity": "sha512-dP6PCG+OwR6RtFpOqwPsLnfiCr3CwXAm/SVGMbO53vDAk0nhUQ1WGAyHDYmIyMAkaLJkIKGwDnX7XmZ5+yAg7g==",
      "requires": {
        "@types/express": "^4.17.0",
        "cors": "^2.8.5",
        "express": "^4.17.1",
        "jsonwebtoken": "^8.5.1",
        "lodash": "^4.17.14"
      },
      "dependencies": {
        "jsonwebtoken": {
          "version": "8.5.1",
          "resolved": "https://registry.npmjs.org/jsonwebtoken/-/jsonwebtoken-8.5.1.tgz",
          "integrity": "sha512-XjwVfRS6jTMsqYs0EsuJ4LGxXV14zQybNd4L2r0UvbVnSF9Af8x7p5MzbJ90Ioz/9TI41/hTCvznF/loiSzn8w==",
          "requires": {
            "jws": "^3.2.2",
            "lodash.includes": "^4.3.0",
            "lodash.isboolean": "^3.0.3",
            "lodash.isinteger": "^4.0.4",
            "lodash.isnumber": "^3.0.3",
            "lodash.isplainobject": "^4.0.6",
            "lodash.isstring": "^4.0.1",
            "lodash.once": "^4.0.0",
            "ms": "^2.1.1",
            "semver": "^5.6.0"
          }
        },
        "semver": {
          "version": "5.7.1",
          "resolved": "https://registry.npmjs.org/semver/-/semver-5.7.1.tgz",
          "integrity": "sha512-sauaDf/PZdVgrLTNYHRtpXa1iRiKcaebiKQ1BJdpQlWH2lCvexQdX55snPFyK7QzpudqbCI0qXFfOasHdyNDGQ=="
        }
      }
    },
    "firebase-functions-test": {
      "version": "0.1.6",
      "resolved": "https://registry.npmjs.org/firebase-functions-test/-/firebase-functions-test-0.1.6.tgz",
      "integrity": "sha512-sITLbQunI75gL690qFOq4mqxUEcdETEbY4HcLFawWVJC3PmlSFt81mhfZjJe45GJTt1+7xeowaHQx3jpnoPNpA==",
      "dev": true,
      "requires": {
        "@types/lodash": "^4.14.104",
        "lodash": "^4.17.5"
      }
    },
    "flat-cache": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/flat-cache/-/flat-cache-2.0.1.tgz",
      "integrity": "sha512-LoQe6yDuUMDzQAEH8sgmh4Md6oZnc/7PjtwjNFSzveXqSHt6ka9fPBuso7IGf9Rz4uqnSnWiFH2B/zj24a5ReA==",
      "dev": true,
      "requires": {
        "flatted": "^2.0.0",
        "rimraf": "2.6.3",
        "write": "1.0.3"
      }
    },
    "flatted": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/flatted/-/flatted-2.0.1.tgz",
      "integrity": "sha512-a1hQMktqW9Nmqr5aktAux3JMNqaucxGcjtjWnZLHX7yyPCmlSV3M54nGYbqT8K+0GhF3NBgmJCc3ma+WOgX8Jg==",
      "dev": true
    },
    "forwarded": {
      "version": "0.1.2",
      "resolved": "https://registry.npmjs.org/forwarded/-/forwarded-0.1.2.tgz",
      "integrity": "sha1-mMI9qxF1ZXuMBXPozszZGw/xjIQ="
    },
    "fresh": {
      "version": "0.5.2",
      "resolved": "https://registry.npmjs.org/fresh/-/fresh-0.5.2.tgz",
      "integrity": "sha1-PYyt2Q2XZWn6g1qx+OSyOhBWBac="
    },
    "fs.realpath": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/fs.realpath/-/fs.realpath-1.0.0.tgz",
      "integrity": "sha1-FQStJSMVjKpA20onh8sBQRmU6k8=",
      "dev": true
    },
    "function-bind": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/function-bind/-/function-bind-1.1.1.tgz",
      "integrity": "sha512-yIovAzMX49sF8Yl58fSCWJ5svSLuaibPxXQJFLmBObTuCr0Mf1KiPopGM9NiFjiYBCbfaa2Fh6breQ6ANVTI0A==",
      "optional": true
    },
    "functional-red-black-tree": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/functional-red-black-tree/-/functional-red-black-tree-1.0.1.tgz",
      "integrity": "sha1-GwqzvVU7Kg1jmdKcDj6gslIHgyc="
    },
    "gaxios": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/gaxios/-/gaxios-2.0.1.tgz",
      "integrity": "sha512-c1NXovTxkgRJTIgB2FrFmOFg4YIV6N/bAa4f/FZ4jIw13Ql9ya/82x69CswvotJhbV3DiGnlTZwoq2NVXk2Irg==",
      "optional": true,
      "requires": {
        "abort-controller": "^3.0.0",
        "extend": "^3.0.2",
        "https-proxy-agent": "^2.2.1",
        "node-fetch": "^2.3.0"
      }
    },
    "gcp-metadata": {
      "version": "3.2.0",
      "resolved": "https://registry.npmjs.org/gcp-metadata/-/gcp-metadata-3.2.0.tgz",
      "integrity": "sha512-ympv+yQ6k5QuWCuwQqnGEvFGS7MBKdcQdj1i188v3bW9QLFIchTGaBCEZxSQapT0jffdn1vdt8oJhB5VBWQO1Q==",
      "optional": true,
      "requires": {
        "gaxios": "^2.0.1",
        "json-bigint": "^0.3.0"
      }
    },
    "gcs-resumable-upload": {
      "version": "2.2.5",
      "resolved": "https://registry.npmjs.org/gcs-resumable-upload/-/gcs-resumable-upload-2.2.5.tgz",
      "integrity": "sha512-r98Hnxza8oYT21MzpziAB2thz3AURGz54+osWtczxGNxH7Fodb0HVUEtfqTwBS5vcf9RnKwR7c0EMaI8R39feg==",
      "optional": true,
      "requires": {
        "abort-controller": "^3.0.0",
        "configstore": "^5.0.0",
        "gaxios": "^2.0.0",
        "google-auth-library": "^5.0.0",
        "pumpify": "^2.0.0",
        "stream-events": "^1.0.4"
      }
    },
    "glob": {
      "version": "7.1.4",
      "resolved": "https://registry.npmjs.org/glob/-/glob-7.1.4.tgz",
      "integrity": "sha512-hkLPepehmnKk41pUGm3sYxoFs/umurYfYJCerbXEyFIWcAzvpipAgVkBqqT9RBKMGjnq6kMuyYwha6csxbiM1A==",
      "dev": true,
      "requires": {
        "fs.realpath": "^1.0.0",
        "inflight": "^1.0.4",
        "inherits": "2",
        "minimatch": "^3.0.4",
        "once": "^1.3.0",
        "path-is-absolute": "^1.0.0"
      }
    },
    "globals": {
      "version": "11.12.0",
      "resolved": "https://registry.npmjs.org/globals/-/globals-11.12.0.tgz",
      "integrity": "sha512-WOBp/EEGUiIsJSp7wcv/y6MO+lV9UoncWqxuFfm8eBwzWNgyfBd6Gz+IeKQ9jCmyhoH99g15M3T+QaVHFjizVA==",
      "dev": true
    },
    "google-auth-library": {
      "version": "5.4.1",
      "resolved": "https://registry.npmjs.org/google-auth-library/-/google-auth-library-5.4.1.tgz",
      "integrity": "sha512-0KsKBGvlPBNHBkLmw2dfYWDHTuCGCWJrDTzzbYbJO8/ZfcEQ4RJ9Xo1Tnba0a/ZCxPHUkpHqBMB/aRTvnNvxPg==",
      "optional": true,
      "requires": {
        "arrify": "^2.0.0",
        "base64-js": "^1.3.0",
        "fast-text-encoding": "^1.0.0",
        "gaxios": "^2.0.0",
        "gcp-metadata": "^3.2.0",
        "gtoken": "^4.1.0",
        "jws": "^3.1.5",
        "lru-cache": "^5.0.0"
      }
    },
    "google-gax": {
      "version": "1.7.4",
      "resolved": "https://registry.npmjs.org/google-gax/-/google-gax-1.7.4.tgz",
      "integrity": "sha512-K790wkaEuAeZwfT3yF+oM5Y8foPNErNTzPLMU7qL5THsGYmZHlLpoqwHF9kWxY9pZDwOo3xip34tmCte17lP6w==",
      "optional": true,
      "requires": {
        "@grpc/grpc-js": "0.6.8",
        "@grpc/proto-loader": "^0.5.1",
        "abort-controller": "^3.0.0",
        "duplexify": "^3.6.0",
        "google-auth-library": "^5.0.0",
        "is-stream-ended": "^0.1.4",
        "lodash.at": "^4.6.0",
        "lodash.has": "^4.5.2",
        "node-fetch": "^2.6.0",
        "protobufjs": "^6.8.8",
        "retry-request": "^4.0.0",
        "semver": "^6.0.0",
        "walkdir": "^0.4.0"
      }
    },
    "google-p12-pem": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/google-p12-pem/-/google-p12-pem-2.0.2.tgz",
      "integrity": "sha512-UfnEARfJKI6pbmC1hfFFm+UAcZxeIwTiEcHfqKe/drMsXD/ilnVjF7zgOGpHXyhuvX6jNJK3S8A0hOQjwtFxEw==",
      "optional": true,
      "requires": {
        "node-forge": "^0.9.0"
      },
      "dependencies": {
        "node-forge": {
          "version": "0.9.1",
          "resolved": "https://registry.npmjs.org/node-forge/-/node-forge-0.9.1.tgz",
          "integrity": "sha512-G6RlQt5Sb4GMBzXvhfkeFmbqR6MzhtnT7VTHuLadjkii3rdYHNdw0m8zA4BTxVIh68FicCQ2NSUANpsqkr9jvQ==",
          "optional": true
        }
      }
    },
    "graceful-fs": {
      "version": "4.2.2",
      "resolved": "https://registry.npmjs.org/graceful-fs/-/graceful-fs-4.2.2.tgz",
      "integrity": "sha512-IItsdsea19BoLC7ELy13q1iJFNmd7ofZH5+X/pJr90/nRoPEX0DJo1dHDbgtYWOhJhcCgMDTOw84RZ72q6lB+Q==",
      "optional": true
    },
    "gtoken": {
      "version": "4.1.0",
      "resolved": "https://registry.npmjs.org/gtoken/-/gtoken-4.1.0.tgz",
      "integrity": "sha512-wqyn2gf5buzEZN4QNmmiiW2i2JkEdZnL7Z/9p44RtZqgt4077m4khRgAYNuu8cBwHWCc6MsP6eDUn/KkF6jFIw==",
      "optional": true,
      "requires": {
        "gaxios": "^2.0.0",
        "google-p12-pem": "^2.0.0",
        "jws": "^3.1.5",
        "mime": "^2.2.0"
      }
    },
    "has": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/has/-/has-1.0.3.tgz",
      "integrity": "sha512-f2dvO0VU6Oej7RkWJGrehjbzMAjFp5/VKPp5tTpWIV4JHHZK1/BxbFRtf/siA2SWTe09caDmVtYYzWEIbBS4zw==",
      "optional": true,
      "requires": {
        "function-bind": "^1.1.1"
      }
    },
    "has-flag": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/has-flag/-/has-flag-3.0.0.tgz",
      "integrity": "sha1-tdRU3CGZriJWmfNGfloH87lVuv0=",
      "dev": true
    },
    "hash-stream-validation": {
      "version": "0.2.2",
      "resolved": "https://registry.npmjs.org/hash-stream-validation/-/hash-stream-validation-0.2.2.tgz",
      "integrity": "sha512-cMlva5CxWZOrlS/cY0C+9qAzesn5srhFA8IT1VPiHc9bWWBLkJfEUIZr7MWoi89oOOGmpg8ymchaOjiArsGu5A==",
      "optional": true,
      "requires": {
        "through2": "^2.0.0"
      },
      "dependencies": {
        "isarray": {
          "version": "1.0.0",
          "resolved": "https://registry.npmjs.org/isarray/-/isarray-1.0.0.tgz",
          "integrity": "sha1-u5NdSFgsuhaMBoNJV6VKPgcSTxE=",
          "optional": true
        },
        "readable-stream": {
          "version": "2.3.6",
          "resolved": "https://registry.npmjs.org/readable-stream/-/readable-stream-2.3.6.tgz",
          "integrity": "sha512-tQtKA9WIAhBF3+VLAseyMqZeBjW0AHJoxOtYqSUZNJxauErmLbVm2FW1y+J/YA9dUrAC39ITejlZWhVIwawkKw==",
          "optional": true,
          "requires": {
            "core-util-is": "~1.0.0",
            "inherits": "~2.0.3",
            "isarray": "~1.0.0",
            "process-nextick-args": "~2.0.0",
            "safe-buffer": "~5.1.1",
            "string_decoder": "~1.1.1",
            "util-deprecate": "~1.0.1"
          }
        },
        "safe-buffer": {
          "version": "5.1.2",
          "resolved": "https://registry.npmjs.org/safe-buffer/-/safe-buffer-5.1.2.tgz",
          "integrity": "sha512-Gd2UZBJDkXlY7GbJxfsE8/nvKkUEU1G38c1siN6QP6a9PT9MmHB8GnpscSmMJSoF8LOIrt8ud/wPtojys4G6+g==",
          "optional": true
        },
        "string_decoder": {
          "version": "1.1.1",
          "resolved": "https://registry.npmjs.org/string_decoder/-/string_decoder-1.1.1.tgz",
          "integrity": "sha512-n/ShnvDi6FHbbVfviro+WojiFzv+s8MPMHBczVePfUpDJLwoLT0ht1l4YwBCbi8pJAveEEdnkHyPyTP/mzRfwg==",
          "optional": true,
          "requires": {
            "safe-buffer": "~5.1.0"
          }
        },
        "through2": {
          "version": "2.0.5",
          "resolved": "https://registry.npmjs.org/through2/-/through2-2.0.5.tgz",
          "integrity": "sha512-/mrRod8xqpA+IHSLyGCQ2s8SPHiCDEeQJSep1jqLYeEUClOFG2Qsh+4FU6G9VeqpZnGW/Su8LQGc4YKni5rYSQ==",
          "optional": true,
          "requires": {
            "readable-stream": "~2.3.6",
            "xtend": "~4.0.1"
          }
        }
      }
    },
    "http-errors": {
      "version": "1.7.2",
      "resolved": "https://registry.npmjs.org/http-errors/-/http-errors-1.7.2.tgz",
      "integrity": "sha512-uUQBt3H/cSIVfch6i1EuPNy/YsRSOUBXTVfZ+yR7Zjez3qjBz6i9+i4zjNaoqcoFVI4lQJ5plg63TvGfRSDCRg==",
      "requires": {
        "depd": "~1.1.2",
        "inherits": "2.0.3",
        "setprototypeof": "1.1.1",
        "statuses": ">= 1.5.0 < 2",
        "toidentifier": "1.0.0"
      },
      "dependencies": {
        "inherits": {
          "version": "2.0.3",
          "resolved": "https://registry.npmjs.org/inherits/-/inherits-2.0.3.tgz",
          "integrity": "sha1-Yzwsg+PaQqUC9SRmAiSA9CCCYd4="
        }
      }
    },
    "http-parser-js": {
      "version": "0.4.10",
      "resolved": "https://registry.npmjs.org/http-parser-js/-/http-parser-js-0.4.10.tgz",
      "integrity": "sha1-ksnBN0w1CF912zWexWzCV8u5P6Q="
    },
    "http-proxy-agent": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/http-proxy-agent/-/http-proxy-agent-2.1.0.tgz",
      "integrity": "sha512-qwHbBLV7WviBl0rQsOzH6o5lwyOIvwp/BdFnvVxXORldu5TmjFfjzBcWUWS5kWAZhmv+JtiDhSuQCp4sBfbIgg==",
      "optional": true,
      "requires": {
        "agent-base": "4",
        "debug": "3.1.0"
      },
      "dependencies": {
        "debug": {
          "version": "3.1.0",
          "resolved": "https://registry.npmjs.org/debug/-/debug-3.1.0.tgz",
          "integrity": "sha512-OX8XqP7/1a9cqkxYw2yXss15f26NKWBpDXQd0/uK/KPqdQhxbPa994hnzjcE2VqQpDslf55723cKPUOGSmMY3g==",
          "optional": true,
          "requires": {
            "ms": "2.0.0"
          }
        },
        "ms": {
          "version": "2.0.0",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.0.0.tgz",
          "integrity": "sha1-VgiurfwAvmwpAd9fmGF4jeDVl8g=",
          "optional": true
        }
      }
    },
    "https-proxy-agent": {
      "version": "2.2.2",
      "resolved": "https://registry.npmjs.org/https-proxy-agent/-/https-proxy-agent-2.2.2.tgz",
      "integrity": "sha512-c8Ndjc9Bkpfx/vCJueCPy0jlP4ccCCSNDp8xwCZzPjKJUm+B+u9WX2x98Qx4n1PiMNTWo3D7KK5ifNV/yJyRzg==",
      "optional": true,
      "requires": {
        "agent-base": "^4.3.0",
        "debug": "^3.1.0"
      }
    },
    "iconv-lite": {
      "version": "0.4.24",
      "resolved": "https://registry.npmjs.org/iconv-lite/-/iconv-lite-0.4.24.tgz",
      "integrity": "sha512-v3MXnZAcvnywkTUEZomIActle7RXXeedOR31wwl7VlyoXO4Qi9arvSenNQWne1TcRwhCL1HwLI21bEqdpj8/rA==",
      "requires": {
        "safer-buffer": ">= 2.1.2 < 3"
      }
    },
    "ignore": {
      "version": "4.0.6",
      "resolved": "https://registry.npmjs.org/ignore/-/ignore-4.0.6.tgz",
      "integrity": "sha512-cyFDKrqc/YdcWFniJhzI42+AzS+gNwmUzOSFcRCQYwySuBBBy/KjuxWLZ/FHEH6Moq1NizMOBWyTcv8O4OZIMg==",
      "dev": true
    },
    "import-fresh": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/import-fresh/-/import-fresh-3.1.0.tgz",
      "integrity": "sha512-PpuksHKGt8rXfWEr9m9EHIpgyyaltBy8+eF6GJM0QCAxMgxCfucMF3mjecK2QsJr0amJW7gTqh5/wht0z2UhEQ==",
      "dev": true,
      "requires": {
        "parent-module": "^1.0.0",
        "resolve-from": "^4.0.0"
      }
    },
    "imurmurhash": {
      "version": "0.1.4",
      "resolved": "https://registry.npmjs.org/imurmurhash/-/imurmurhash-0.1.4.tgz",
      "integrity": "sha1-khi5srkoojixPcT7a21XbyMUU+o="
    },
    "inflight": {
      "version": "1.0.6",
      "resolved": "https://registry.npmjs.org/inflight/-/inflight-1.0.6.tgz",
      "integrity": "sha1-Sb1jMdfQLQwJvJEKEHW6gWW1bfk=",
      "dev": true,
      "requires": {
        "once": "^1.3.0",
        "wrappy": "1"
      }
    },
    "inherits": {
      "version": "2.0.4",
      "resolved": "https://registry.npmjs.org/inherits/-/inherits-2.0.4.tgz",
      "integrity": "sha512-k/vGaX4/Yla3WzyMCvTQOXYeIHvqOKtnqBduzTHpzpQZzAskKMhZ2K+EnBiSM9zGSoIFeMpXKxa4dYeZIQqewQ=="
    },
    "inquirer": {
      "version": "6.5.2",
      "resolved": "https://registry.npmjs.org/inquirer/-/inquirer-6.5.2.tgz",
      "integrity": "sha512-cntlB5ghuB0iuO65Ovoi8ogLHiWGs/5yNrtUcKjFhSSiVeAIVpD7koaSU9RM8mpXw5YDi9RdYXGQMaOURB7ycQ==",
      "dev": true,
      "requires": {
        "ansi-escapes": "^3.2.0",
        "chalk": "^2.4.2",
        "cli-cursor": "^2.1.0",
        "cli-width": "^2.0.0",
        "external-editor": "^3.0.3",
        "figures": "^2.0.0",
        "lodash": "^4.17.12",
        "mute-stream": "0.0.7",
        "run-async": "^2.2.0",
        "rxjs": "^6.4.0",
        "string-width": "^2.1.0",
        "strip-ansi": "^5.1.0",
        "through": "^2.3.6"
      },
      "dependencies": {
        "ansi-regex": {
          "version": "4.1.0",
          "resolved": "https://registry.npmjs.org/ansi-regex/-/ansi-regex-4.1.0.tgz",
          "integrity": "sha512-1apePfXM1UOSqw0o9IiFAovVz9M5S1Dg+4TrDwfMewQ6p/rmMueb7tWZjQ1rx4Loy1ArBggoqGpfqqdI4rondg==",
          "dev": true
        },
        "strip-ansi": {
          "version": "5.2.0",
          "resolved": "https://registry.npmjs.org/strip-ansi/-/strip-ansi-5.2.0.tgz",
          "integrity": "sha512-DuRs1gKbBqsMKIZlrffwlug8MHkcnpjs5VPmL1PAh+mA30U0DTotfDZ0d2UUsXpPmPmMMJ6W773MaA3J+lbiWA==",
          "dev": true,
          "requires": {
            "ansi-regex": "^4.1.0"
          }
        }
      }
    },
    "ipaddr.js": {
      "version": "1.9.0",
      "resolved": "https://registry.npmjs.org/ipaddr.js/-/ipaddr.js-1.9.0.tgz",
      "integrity": "sha512-M4Sjn6N/+O6/IXSJseKqHoFc+5FdGJ22sXqnjTpdZweHK64MzEPAyQZyEU3R/KRv2GLoa7nNtg/C2Ev6m7z+eA=="
    },
    "is-arguments": {
      "version": "1.0.4",
      "resolved": "https://registry.npmjs.org/is-arguments/-/is-arguments-1.0.4.tgz",
      "integrity": "sha512-xPh0Rmt8NE65sNzvyUmWgI1tz3mKq74lGA0mL8LYZcoIzKOzDh6HmrYm3d18k60nHerC8A9Km8kYu87zfSFnLA==",
      "optional": true
    },
    "is-date-object": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/is-date-object/-/is-date-object-1.0.1.tgz",
      "integrity": "sha1-mqIOtq7rv/d/vTPnTKAbM1gdOhY=",
      "optional": true
    },
    "is-fullwidth-code-point": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/is-fullwidth-code-point/-/is-fullwidth-code-point-2.0.0.tgz",
      "integrity": "sha1-o7MKXE8ZkYMWeqq5O+764937ZU8=",
      "dev": true
    },
    "is-obj": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/is-obj/-/is-obj-2.0.0.tgz",
      "integrity": "sha512-drqDG3cbczxxEJRoOXcOjtdp1J/lyp1mNn0xaznRs8+muBhgQcrnbspox5X5fOw0HnMnbfDzvnEMEtqDEJEo8w==",
      "optional": true
    },
    "is-promise": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/is-promise/-/is-promise-2.1.0.tgz",
      "integrity": "sha1-eaKp7OfwlugPNtKy87wWwf9L8/o=",
      "dev": true
    },
    "is-regex": {
      "version": "1.0.4",
      "resolved": "https://registry.npmjs.org/is-regex/-/is-regex-1.0.4.tgz",
      "integrity": "sha1-VRdIm1RwkbCTDglWVM7SXul+lJE=",
      "optional": true,
      "requires": {
        "has": "^1.0.1"
      }
    },
    "is-stream-ended": {
      "version": "0.1.4",
      "resolved": "https://registry.npmjs.org/is-stream-ended/-/is-stream-ended-0.1.4.tgz",
      "integrity": "sha512-xj0XPvmr7bQFTvirqnFr50o0hQIh6ZItDqloxt5aJrR4NQsYeSsyFQERYGCAzfindAcnKjINnwEEgLx4IqVzQw==",
      "optional": true
    },
    "is-typedarray": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/is-typedarray/-/is-typedarray-1.0.0.tgz",
      "integrity": "sha1-5HnICFjfDBsR3dppQPlgEfzaSpo=",
      "optional": true
    },
    "isarray": {
      "version": "0.0.1",
      "resolved": "https://registry.npmjs.org/isarray/-/isarray-0.0.1.tgz",
      "integrity": "sha1-ihis/Kmo9Bd+Cav8YDiTmwXR7t8=",
      "optional": true
    },
    "isexe": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/isexe/-/isexe-2.0.0.tgz",
      "integrity": "sha1-6PvzdNxVb/iUehDcsFctYz8s+hA=",
      "dev": true
    },
    "js-tokens": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/js-tokens/-/js-tokens-4.0.0.tgz",
      "integrity": "sha512-RdJUflcE3cUzKiMqQgsCu06FPu9UdIJO0beYbPhHN4k6apgJtifcoCtT9bcxOpYBtpD2kCM6Sbzg4CausW/PKQ==",
      "dev": true
    },
    "js-yaml": {
      "version": "3.13.1",
      "resolved": "https://registry.npmjs.org/js-yaml/-/js-yaml-3.13.1.tgz",
      "integrity": "sha512-YfbcO7jXDdyj0DGxYVSlSeQNHbD7XPWvrVWeVUujrQEoZzWJIRrCPoyk6kL6IAjAG2IolMK4T0hNUe0HOUs5Jw==",
      "dev": true,
      "requires": {
        "argparse": "^1.0.7",
        "esprima": "^4.0.0"
      }
    },
    "json-bigint": {
      "version": "0.3.0",
      "resolved": "https://registry.npmjs.org/json-bigint/-/json-bigint-0.3.0.tgz",
      "integrity": "sha1-DM2RLEuCcNBfBW+9E4FLU9OCWx4=",
      "optional": true,
      "requires": {
        "bignumber.js": "^7.0.0"
      }
    },
    "json-schema-traverse": {
      "version": "0.4.1",
      "resolved": "https://registry.npmjs.org/json-schema-traverse/-/json-schema-traverse-0.4.1.tgz",
      "integrity": "sha512-xbbCH5dCYU5T8LcEhhuh7HJ88HXuW3qsI3Y0zOZFKfZEHcpWiHU/Jxzk629Brsab/mMiHQti9wMP+845RPe3Vg==",
      "dev": true
    },
    "json-stable-stringify-without-jsonify": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/json-stable-stringify-without-jsonify/-/json-stable-stringify-without-jsonify-1.0.1.tgz",
      "integrity": "sha1-nbe1lJatPzz+8wp1FC0tkwrXJlE=",
      "dev": true
    },
    "jsonwebtoken": {
      "version": "8.1.0",
      "resolved": "https://registry.npmjs.org/jsonwebtoken/-/jsonwebtoken-8.1.0.tgz",
      "integrity": "sha1-xjl80uX9WD1lwAeoPce7eOaYK4M=",
      "requires": {
        "jws": "^3.1.4",
        "lodash.includes": "^4.3.0",
        "lodash.isboolean": "^3.0.3",
        "lodash.isinteger": "^4.0.4",
        "lodash.isnumber": "^3.0.3",
        "lodash.isplainobject": "^4.0.6",
        "lodash.isstring": "^4.0.1",
        "lodash.once": "^4.0.0",
        "ms": "^2.0.0",
        "xtend": "^4.0.1"
      }
    },
    "jwa": {
      "version": "1.4.1",
      "resolved": "https://registry.npmjs.org/jwa/-/jwa-1.4.1.tgz",
      "integrity": "sha512-qiLX/xhEEFKUAJ6FiBMbes3w9ATzyk5W7Hvzpa/SLYdxNtng+gcurvrI7TbACjIXlsJyr05/S1oUhZrc63evQA==",
      "requires": {
        "buffer-equal-constant-time": "1.0.1",
        "ecdsa-sig-formatter": "1.0.11",
        "safe-buffer": "^5.0.1"
      }
    },
    "jws": {
      "version": "3.2.2",
      "resolved": "https://registry.npmjs.org/jws/-/jws-3.2.2.tgz",
      "integrity": "sha512-YHlZCB6lMTllWDtSPHz/ZXTsi8S00usEV6v1tjq8tOUZzw7DpSDWVXjXDre6ed1w/pd495ODpHZYSdkRTsa0HA==",
      "requires": {
        "jwa": "^1.4.1",
        "safe-buffer": "^5.0.1"
      }
    },
    "levn": {
      "version": "0.3.0",
      "resolved": "https://registry.npmjs.org/levn/-/levn-0.3.0.tgz",
      "integrity": "sha1-OwmSTt+fCDwEkP3UwLxEIeBHZO4=",
      "dev": true,
      "requires": {
        "prelude-ls": "~1.1.2",
        "type-check": "~0.3.2"
      }
    },
    "lodash": {
      "version": "4.17.15",
      "resolved": "https://registry.npmjs.org/lodash/-/lodash-4.17.15.tgz",
      "integrity": "sha512-8xOcRHvCjnocdS5cpwXQXVzmmh5e5+saE2QGoeQmbKmRS6J3VQppPOIt0MnmE+4xlZoumy0GPG0D0MVIQbNA1A=="
    },
    "lodash.at": {
      "version": "4.6.0",
      "resolved": "https://registry.npmjs.org/lodash.at/-/lodash.at-4.6.0.tgz",
      "integrity": "sha1-k83OZk8KGZTqM9181A4jr9EbD/g=",
      "optional": true
    },
    "lodash.camelcase": {
      "version": "4.3.0",
      "resolved": "https://registry.npmjs.org/lodash.camelcase/-/lodash.camelcase-4.3.0.tgz",
      "integrity": "sha1-soqmKIorn8ZRA1x3EfZathkDMaY=",
      "optional": true
    },
    "lodash.has": {
      "version": "4.5.2",
      "resolved": "https://registry.npmjs.org/lodash.has/-/lodash.has-4.5.2.tgz",
      "integrity": "sha1-0Z9NwQlQWMzL4rDN9O4P5Ko3yGI=",
      "optional": true
    },
    "lodash.includes": {
      "version": "4.3.0",
      "resolved": "https://registry.npmjs.org/lodash.includes/-/lodash.includes-4.3.0.tgz",
      "integrity": "sha1-YLuYqHy5I8aMoeUTJUgzFISfVT8="
    },
    "lodash.isboolean": {
      "version": "3.0.3",
      "resolved": "https://registry.npmjs.org/lodash.isboolean/-/lodash.isboolean-3.0.3.tgz",
      "integrity": "sha1-bC4XHbKiV82WgC/UOwGyDV9YcPY="
    },
    "lodash.isinteger": {
      "version": "4.0.4",
      "resolved": "https://registry.npmjs.org/lodash.isinteger/-/lodash.isinteger-4.0.4.tgz",
      "integrity": "sha1-YZwK89A/iwTDH1iChAt3sRzWg0M="
    },
    "lodash.isnumber": {
      "version": "3.0.3",
      "resolved": "https://registry.npmjs.org/lodash.isnumber/-/lodash.isnumber-3.0.3.tgz",
      "integrity": "sha1-POdoEMWSjQM1IwGsKHMX8RwLH/w="
    },
    "lodash.isplainobject": {
      "version": "4.0.6",
      "resolved": "https://registry.npmjs.org/lodash.isplainobject/-/lodash.isplainobject-4.0.6.tgz",
      "integrity": "sha1-fFJqUtibRcRcxpC4gWO+BJf1UMs="
    },
    "lodash.isstring": {
      "version": "4.0.1",
      "resolved": "https://registry.npmjs.org/lodash.isstring/-/lodash.isstring-4.0.1.tgz",
      "integrity": "sha1-1SfftUVuynzJu5XV2ur4i6VKVFE="
    },
    "lodash.once": {
      "version": "4.1.1",
      "resolved": "https://registry.npmjs.org/lodash.once/-/lodash.once-4.1.1.tgz",
      "integrity": "sha1-DdOXEhPHxW34gJd9UEyI+0cal6w="
    },
    "long": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/long/-/long-4.0.0.tgz",
      "integrity": "sha512-XsP+KhQif4bjX1kbuSiySJFNAehNxgLb6hPRGJ9QsUr8ajHkuXGdrHmFUTUUXhDwVX2R5bY4JNZEwbUiMhV+MA==",
      "optional": true
    },
    "lru-cache": {
      "version": "5.1.1",
      "resolved": "https://registry.npmjs.org/lru-cache/-/lru-cache-5.1.1.tgz",
      "integrity": "sha512-KpNARQA3Iwv+jTA0utUVVbrh+Jlrr1Fv0e56GGzAFOXN7dk/FviaDW8LHmK52DlcH4WP2n6gI8vN1aesBFgo9w==",
      "optional": true,
      "requires": {
        "yallist": "^3.0.2"
      }
    },
    "make-dir": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/make-dir/-/make-dir-3.0.0.tgz",
      "integrity": "sha512-grNJDhb8b1Jm1qeqW5R/O63wUo4UXo2v2HMic6YT9i/HBlF93S8jkMgH7yugvY9ABDShH4VZMn8I+U8+fCNegw==",
      "optional": true,
      "requires": {
        "semver": "^6.0.0"
      }
    },
    "media-typer": {
      "version": "0.3.0",
      "resolved": "https://registry.npmjs.org/media-typer/-/media-typer-0.3.0.tgz",
      "integrity": "sha1-hxDXrwqmJvj/+hzgAWhUUmMlV0g="
    },
    "merge-descriptors": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/merge-descriptors/-/merge-descriptors-1.0.1.tgz",
      "integrity": "sha1-sAqqVW3YtEVoFQ7J0blT8/kMu2E="
    },
    "methods": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/methods/-/methods-1.1.2.tgz",
      "integrity": "sha1-VSmk1nZUE07cxSZmVoNbD4Ua/O4="
    },
    "mime": {
      "version": "2.4.4",
      "resolved": "https://registry.npmjs.org/mime/-/mime-2.4.4.tgz",
      "integrity": "sha512-LRxmNwziLPT828z+4YkNzloCFC2YM4wrB99k+AV5ZbEyfGNWfG8SO1FUXLmLDBSo89NrJZ4DIWeLjy1CHGhMGA==",
      "optional": true
    },
    "mime-db": {
      "version": "1.42.0",
      "resolved": "https://registry.npmjs.org/mime-db/-/mime-db-1.42.0.tgz",
      "integrity": "sha512-UbfJCR4UAVRNgMpfImz05smAXK7+c+ZntjaA26ANtkXLlOe947Aag5zdIcKQULAiF9Cq4WxBi9jUs5zkA84bYQ==",
      "optional": true
    },
    "mime-types": {
      "version": "2.1.24",
      "resolved": "https://registry.npmjs.org/mime-types/-/mime-types-2.1.24.tgz",
      "integrity": "sha512-WaFHS3MCl5fapm3oLxU4eYDw77IQM2ACcxQ9RIxfaC3ooc6PFuBMGZZsYpvoXS5D5QTWPieo1jjLdAm3TBP3cQ==",
      "requires": {
        "mime-db": "1.40.0"
      },
      "dependencies": {
        "mime-db": {
          "version": "1.40.0",
          "resolved": "https://registry.npmjs.org/mime-db/-/mime-db-1.40.0.tgz",
          "integrity": "sha512-jYdeOMPy9vnxEqFRRo6ZvTZ8d9oPb+k18PKoYNYUe2stVEBPPwsln/qWzdbmaIvnhZ9v2P+CuecK+fpUfsV2mA=="
        }
      }
    },
    "mimic-fn": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/mimic-fn/-/mimic-fn-2.1.0.tgz",
      "integrity": "sha512-OqbOk5oEQeAZ8WXWydlu9HJjz9WVdEIvamMCcXmuqUYjTknH/sqsWvhQ3vgwKFRR1HpjvNBKQ37nbJgYzGqGcg==",
      "optional": true
    },
    "minimatch": {
      "version": "3.0.4",
      "resolved": "https://registry.npmjs.org/minimatch/-/minimatch-3.0.4.tgz",
      "integrity": "sha512-yJHVQEhyqPLUTgt9B83PXu6W3rx4MvvHvSUvToogpwoGDOUQ+yDrR0HRot+yOCdCO7u4hX3pWft6kWBBcqh0UA==",
      "dev": true,
      "requires": {
        "brace-expansion": "^1.1.7"
      }
    },
    "minimist": {
      "version": "0.0.8",
      "resolved": "https://registry.npmjs.org/minimist/-/minimist-0.0.8.tgz",
      "integrity": "sha1-hX/Kv8M5fSYluCKCYuhqp6ARsF0=",
      "dev": true
    },
    "mkdirp": {
      "version": "0.5.1",
      "resolved": "https://registry.npmjs.org/mkdirp/-/mkdirp-0.5.1.tgz",
      "integrity": "sha1-MAV0OOrGz3+MR2fzhkjWaX11yQM=",
      "dev": true,
      "requires": {
        "minimist": "0.0.8"
      }
    },
    "ms": {
      "version": "2.1.2",
      "resolved": "https://registry.npmjs.org/ms/-/ms-2.1.2.tgz",
      "integrity": "sha512-sGkPx+VjMtmA6MX27oA4FBFELFCZZ4S4XqeGOXCv68tT+jb3vk/RyaKWP0PTKyWtmLSM0b+adUTEvbs1PEaH2w=="
    },
    "mute-stream": {
      "version": "0.0.7",
      "resolved": "https://registry.npmjs.org/mute-stream/-/mute-stream-0.0.7.tgz",
      "integrity": "sha1-MHXOk7whuPq0PhvE2n6BFe0ee6s=",
      "dev": true
    },
    "natural-compare": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/natural-compare/-/natural-compare-1.4.0.tgz",
      "integrity": "sha1-Sr6/7tdUHywnrPspvbvRXI1bpPc=",
      "dev": true
    },
    "negotiator": {
      "version": "0.6.2",
      "resolved": "https://registry.npmjs.org/negotiator/-/negotiator-0.6.2.tgz",
      "integrity": "sha512-hZXc7K2e+PgeI1eDBe/10Ard4ekbfrrqG8Ep+8Jmf4JID2bNg7NvCPOZN+kfF574pFQI7mum2AUqDidoKqcTOw=="
    },
    "nice-try": {
      "version": "1.0.5",
      "resolved": "https://registry.npmjs.org/nice-try/-/nice-try-1.0.5.tgz",
      "integrity": "sha512-1nh45deeb5olNY7eX82BkPO7SSxR5SSYJiPTrTdFUVYwAl8CKMA5N9PjTYkHiRjisVcxcQ1HXdLhx2qxxJzLNQ==",
      "dev": true
    },
    "node-fetch": {
      "version": "2.6.0",
      "resolved": "https://registry.npmjs.org/node-fetch/-/node-fetch-2.6.0.tgz",
      "integrity": "sha512-8dG4H5ujfvFiqDmVu9fQ5bOHUC15JMjMY/Zumv26oOvvVJjM67KF8koCWIabKQ1GJIa9r2mMZscBq/TbdOcmNA==",
      "optional": true
    },
    "node-forge": {
      "version": "0.7.4",
      "resolved": "https://registry.npmjs.org/node-forge/-/node-forge-0.7.4.tgz",
      "integrity": "sha512-8Df0906+tq/omxuCZD6PqhPaQDYuyJ1d+VITgxoIA8zvQd1ru+nMJcDChHH324MWitIgbVkAkQoGEEVJNpn/PA=="
    },
    "object-assign": {
      "version": "4.1.1",
      "resolved": "https://registry.npmjs.org/object-assign/-/object-assign-4.1.1.tgz",
      "integrity": "sha1-IQmtx5ZYh8/AXLvUQsrIv7s2CGM="
    },
    "object-is": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/object-is/-/object-is-1.0.1.tgz",
      "integrity": "sha1-CqYOyZiaCz7Xlc9NBvYs8a1lObY=",
      "optional": true
    },
    "object-keys": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/object-keys/-/object-keys-1.1.1.tgz",
      "integrity": "sha512-NuAESUOUMrlIXOfHKzD6bpPu3tYt3xvjNdRIQ+FeT0lNb4K8WR70CaDxhuNguS2XG+GjkyMwOzsN5ZktImfhLA==",
      "optional": true
    },
    "on-finished": {
      "version": "2.3.0",
      "resolved": "https://registry.npmjs.org/on-finished/-/on-finished-2.3.0.tgz",
      "integrity": "sha1-IPEzZIGwg811M3mSoWlxqi2QaUc=",
      "requires": {
        "ee-first": "1.1.1"
      }
    },
    "once": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/once/-/once-1.4.0.tgz",
      "integrity": "sha1-WDsap3WWHUsROsF9nFC6753Xa9E=",
      "requires": {
        "wrappy": "1"
      }
    },
    "onetime": {
      "version": "5.1.0",
      "resolved": "https://registry.npmjs.org/onetime/-/onetime-5.1.0.tgz",
      "integrity": "sha512-5NcSkPHhwTVFIQN+TUqXoS5+dlElHXdpAWu9I0HP20YOtIi+aZ0Ct82jdlILDxjLEAWwvm+qj1m6aEtsDVmm6Q==",
      "optional": true,
      "requires": {
        "mimic-fn": "^2.1.0"
      }
    },
    "optionator": {
      "version": "0.8.2",
      "resolved": "https://registry.npmjs.org/optionator/-/optionator-0.8.2.tgz",
      "integrity": "sha1-NkxeQJ0/TWMB1sC0wFu6UBgK62Q=",
      "dev": true,
      "requires": {
        "deep-is": "~0.1.3",
        "fast-levenshtein": "~2.0.4",
        "levn": "~0.3.0",
        "prelude-ls": "~1.1.2",
        "type-check": "~0.3.2",
        "wordwrap": "~1.0.0"
      }
    },
    "os-tmpdir": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/os-tmpdir/-/os-tmpdir-1.0.2.tgz",
      "integrity": "sha1-u+Z0BseaqFxc/sdm/lc0VV36EnQ=",
      "dev": true
    },
    "p-limit": {
      "version": "2.2.1",
      "resolved": "https://registry.npmjs.org/p-limit/-/p-limit-2.2.1.tgz",
      "integrity": "sha512-85Tk+90UCVWvbDavCLKPOLC9vvY8OwEX/RtKF+/1OADJMVlFfEHOiMTPVyxg7mk/dKa+ipdHm0OUkTvCpMTuwg==",
      "optional": true,
      "requires": {
        "p-try": "^2.0.0"
      }
    },
    "p-try": {
      "version": "2.2.0",
      "resolved": "https://registry.npmjs.org/p-try/-/p-try-2.2.0.tgz",
      "integrity": "sha512-R4nPAVTAU0B9D35/Gk3uJf/7XYbQcyohSKdvAxIRSNghFl4e71hVoGnBNQz9cWaXxO2I10KTC+3jMdvvoKw6dQ==",
      "optional": true
    },
    "parent-module": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/parent-module/-/parent-module-1.0.1.tgz",
      "integrity": "sha512-GQ2EWRpQV8/o+Aw8YqtfZZPfNRWZYkbidE9k5rpl/hC3vtHHBfGm2Ifi6qWV+coDGkrUKZAxE3Lot5kcsRlh+g==",
      "dev": true,
      "requires": {
        "callsites": "^3.0.0"
      }
    },
    "parseurl": {
      "version": "1.3.3",
      "resolved": "https://registry.npmjs.org/parseurl/-/parseurl-1.3.3.tgz",
      "integrity": "sha512-CiyeOxFT/JZyN5m0z9PfXw4SCBJ6Sygz1Dpl0wqjlhDEGGBP1GnsUVEL0p63hoG1fcj3fHynXi9NYO4nWOL+qQ=="
    },
    "path-is-absolute": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/path-is-absolute/-/path-is-absolute-1.0.1.tgz",
      "integrity": "sha1-F0uSaHNVNP+8es5r9TpanhtcX18=",
      "dev": true
    },
    "path-is-inside": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/path-is-inside/-/path-is-inside-1.0.2.tgz",
      "integrity": "sha1-NlQX3t5EQw0cEa9hAn+s8HS9/FM=",
      "dev": true
    },
    "path-key": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/path-key/-/path-key-2.0.1.tgz",
      "integrity": "sha1-QRyttXTFoUDTpLGRDUDYDMn0C0A=",
      "dev": true
    },
    "path-to-regexp": {
      "version": "0.1.7",
      "resolved": "https://registry.npmjs.org/path-to-regexp/-/path-to-regexp-0.1.7.tgz",
      "integrity": "sha1-32BBeABfUi8V60SQ5yR6G/qmf4w="
    },
    "prelude-ls": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/prelude-ls/-/prelude-ls-1.1.2.tgz",
      "integrity": "sha1-IZMqVJ9eUv/ZqCf1cOBL5iqX2lQ=",
      "dev": true
    },
    "process-nextick-args": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/process-nextick-args/-/process-nextick-args-2.0.1.tgz",
      "integrity": "sha512-3ouUOpQhtgrbOa17J7+uxOTpITYWaGP7/AhoR3+A+/1e9skrzelGi/dXzEYyvbxubEF6Wn2ypscTKiKJFFn1ag==",
      "optional": true
    },
    "progress": {
      "version": "2.0.3",
      "resolved": "https://registry.npmjs.org/progress/-/progress-2.0.3.tgz",
      "integrity": "sha512-7PiHtLll5LdnKIMw100I+8xJXR5gW2QwWYkT6iJva0bXitZKa/XMrSbdmg3r2Xnaidz9Qumd0VPaMrZlF9V9sA==",
      "dev": true
    },
    "protobufjs": {
      "version": "6.8.8",
      "resolved": "https://registry.npmjs.org/protobufjs/-/protobufjs-6.8.8.tgz",
      "integrity": "sha512-AAmHtD5pXgZfi7GMpllpO3q1Xw1OYldr+dMUlAnffGTAhqkg72WdmSY71uKBF/JuyiKs8psYbtKrhi0ASCD8qw==",
      "optional": true,
      "requires": {
        "@protobufjs/aspromise": "^1.1.2",
        "@protobufjs/base64": "^1.1.2",
        "@protobufjs/codegen": "^2.0.4",
        "@protobufjs/eventemitter": "^1.1.0",
        "@protobufjs/fetch": "^1.1.0",
        "@protobufjs/float": "^1.0.2",
        "@protobufjs/inquire": "^1.1.0",
        "@protobufjs/path": "^1.1.2",
        "@protobufjs/pool": "^1.1.0",
        "@protobufjs/utf8": "^1.1.0",
        "@types/long": "^4.0.0",
        "@types/node": "^10.1.0",
        "long": "^4.0.0"
      },
      "dependencies": {
        "@types/node": {
          "version": "10.14.21",
          "resolved": "https://registry.npmjs.org/@types/node/-/node-10.14.21.tgz",
          "integrity": "sha512-nuFlRdBiqbF+PJIEVxm2jLFcQWN7q7iWEJGsBV4n7v1dbI9qXB8im2pMMKMCUZe092sQb5SQft2DHfuQGK5hqQ==",
          "optional": true
        }
      }
    },
    "proxy-addr": {
      "version": "2.0.5",
      "resolved": "https://registry.npmjs.org/proxy-addr/-/proxy-addr-2.0.5.tgz",
      "integrity": "sha512-t/7RxHXPH6cJtP0pRG6smSr9QJidhB+3kXu0KgXnbGYMgzEnUxRQ4/LDdfOwZEMyIh3/xHb8PX3t+lfL9z+YVQ==",
      "requires": {
        "forwarded": "~0.1.2",
        "ipaddr.js": "1.9.0"
      }
    },
    "pump": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/pump/-/pump-3.0.0.tgz",
      "integrity": "sha512-LwZy+p3SFs1Pytd/jYct4wpv49HiYCqd9Rlc5ZVdk0V+8Yzv6jR5Blk3TRmPL1ft69TxP0IMZGJ+WPFU2BFhww==",
      "optional": true,
      "requires": {
        "end-of-stream": "^1.1.0",
        "once": "^1.3.1"
      }
    },
    "pumpify": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/pumpify/-/pumpify-2.0.1.tgz",
      "integrity": "sha512-m7KOje7jZxrmutanlkS1daj1dS6z6BgslzOXmcSEpIlCxM3VJH7lG5QLeck/6hgF6F4crFf01UtQmNsJfweTAw==",
      "optional": true,
      "requires": {
        "duplexify": "^4.1.1",
        "inherits": "^2.0.3",
        "pump": "^3.0.0"
      },
      "dependencies": {
        "duplexify": {
          "version": "4.1.1",
          "resolved": "https://registry.npmjs.org/duplexify/-/duplexify-4.1.1.tgz",
          "integrity": "sha512-DY3xVEmVHTv1wSzKNbwoU6nVjzI369Y6sPoqfYr0/xlx3IdX2n94xIszTcjPO8W8ZIv0Wb0PXNcjuZyT4wiICA==",
          "optional": true,
          "requires": {
            "end-of-stream": "^1.4.1",
            "inherits": "^2.0.3",
            "readable-stream": "^3.1.1",
            "stream-shift": "^1.0.0"
          }
        },
        "readable-stream": {
          "version": "3.4.0",
          "resolved": "https://registry.npmjs.org/readable-stream/-/readable-stream-3.4.0.tgz",
          "integrity": "sha512-jItXPLmrSR8jmTRmRWJXCnGJsfy85mB3Wd/uINMXA65yrnFo0cPClFIUWzo2najVNSl+mx7/4W8ttlLWJe99pQ==",
          "optional": true,
          "requires": {
            "inherits": "^2.0.3",
            "string_decoder": "^1.1.1",
            "util-deprecate": "^1.0.1"
          }
        },
        "string_decoder": {
          "version": "1.3.0",
          "resolved": "https://registry.npmjs.org/string_decoder/-/string_decoder-1.3.0.tgz",
          "integrity": "sha512-hkRX8U1WjJFd8LsDJ2yQ/wWWxaopEsABU1XfkM8A+j0+85JAGppt16cr1Whg6KIbb4okU6Mql6BOj+uup/wKeA==",
          "optional": true,
          "requires": {
            "safe-buffer": "~5.2.0"
          }
        }
      }
    },
    "punycode": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/punycode/-/punycode-2.1.1.tgz",
      "integrity": "sha512-XRsRjdf+j5ml+y/6GKHPZbrF/8p2Yga0JPtdqTIY2Xe5ohJPD9saDJJLPvp9+NSBprVvevdXZybnj2cv8OEd0A==",
      "dev": true
    },
    "qs": {
      "version": "6.7.0",
      "resolved": "https://registry.npmjs.org/qs/-/qs-6.7.0.tgz",
      "integrity": "sha512-VCdBRNFTX1fyE7Nb6FYoURo/SPe62QCaAyzJvUjwRaIsc+NePBEniHlvxFmmX56+HZphIGtV0XeCirBtpDrTyQ=="
    },
    "range-parser": {
      "version": "1.2.1",
      "resolved": "https://registry.npmjs.org/range-parser/-/range-parser-1.2.1.tgz",
      "integrity": "sha512-Hrgsx+orqoygnmhFbKaHE6c296J+HTAQXoxEF6gNupROmmGJRoyzfG3ccAveqCBrwr/2yxQ5BVd/GTl5agOwSg=="
    },
    "raw-body": {
      "version": "2.4.0",
      "resolved": "https://registry.npmjs.org/raw-body/-/raw-body-2.4.0.tgz",
      "integrity": "sha512-4Oz8DUIwdvoa5qMJelxipzi/iJIi40O5cGV1wNYp5hvZP8ZN0T+jiNkL0QepXs+EsQ9XJ8ipEDoiH70ySUJP3Q==",
      "requires": {
        "bytes": "3.1.0",
        "http-errors": "1.7.2",
        "iconv-lite": "0.4.24",
        "unpipe": "1.0.0"
      }
    },
    "readable-stream": {
      "version": "1.0.34",
      "resolved": "https://registry.npmjs.org/readable-stream/-/readable-stream-1.0.34.tgz",
      "integrity": "sha1-Elgg40vIQtLyqq+v5MKRbuMsFXw=",
      "optional": true,
      "requires": {
        "core-util-is": "~1.0.0",
        "inherits": "~2.0.1",
        "isarray": "0.0.1",
        "string_decoder": "~0.10.x"
      }
    },
    "regexp.prototype.flags": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/regexp.prototype.flags/-/regexp.prototype.flags-1.2.0.tgz",
      "integrity": "sha512-ztaw4M1VqgMwl9HlPpOuiYgItcHlunW0He2fE6eNfT6E/CF2FtYi9ofOYe4mKntstYk0Fyh/rDRBdS3AnxjlrA==",
      "optional": true,
      "requires": {
        "define-properties": "^1.1.2"
      }
    },
    "regexpp": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/regexpp/-/regexpp-2.0.1.tgz",
      "integrity": "sha512-lv0M6+TkDVniA3aD1Eg0DVpfU/booSu7Eev3TDO/mZKHBfVjgCGTV4t4buppESEYDtkArYFOxTJWv6S5C+iaNw==",
      "dev": true
    },
    "resolve-from": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/resolve-from/-/resolve-from-4.0.0.tgz",
      "integrity": "sha512-pb/MYmXstAkysRFx8piNI1tGFNQIFA3vkE3Gq4EuA1dF6gHp/+vgZqsCGJapvy8N3Q+4o7FwvquPJcnZ7RYy4g==",
      "dev": true
    },
    "restore-cursor": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/restore-cursor/-/restore-cursor-2.0.0.tgz",
      "integrity": "sha1-n37ih/gv0ybU/RYpI9YhKe7g368=",
      "dev": true,
      "requires": {
        "onetime": "^2.0.0",
        "signal-exit": "^3.0.2"
      },
      "dependencies": {
        "mimic-fn": {
          "version": "1.2.0",
          "resolved": "https://registry.npmjs.org/mimic-fn/-/mimic-fn-1.2.0.tgz",
          "integrity": "sha512-jf84uxzwiuiIVKiOLpfYk7N46TSy8ubTonmneY9vrpHNAnp0QBt2BxWV9dO3/j+BoVAb+a5G6YDPW3M5HOdMWQ==",
          "dev": true
        },
        "onetime": {
          "version": "2.0.1",
          "resolved": "https://registry.npmjs.org/onetime/-/onetime-2.0.1.tgz",
          "integrity": "sha1-BnQoIw/WdEOyeUsiu6UotoZ5YtQ=",
          "dev": true,
          "requires": {
            "mimic-fn": "^1.0.0"
          }
        }
      }
    },
    "retry-request": {
      "version": "4.1.1",
      "resolved": "https://registry.npmjs.org/retry-request/-/retry-request-4.1.1.tgz",
      "integrity": "sha512-BINDzVtLI2BDukjWmjAIRZ0oglnCAkpP2vQjM3jdLhmT62h0xnQgciPwBRDAvHqpkPT2Wo1XuUyLyn6nbGrZQQ==",
      "optional": true,
      "requires": {
        "debug": "^4.1.1",
        "through2": "^3.0.1"
      },
      "dependencies": {
        "debug": {
          "version": "4.1.1",
          "resolved": "https://registry.npmjs.org/debug/-/debug-4.1.1.tgz",
          "integrity": "sha512-pYAIzeRo8J6KPEaJ0VWOh5Pzkbw/RetuzehGM7QRRX5he4fPHx2rdKMB256ehJCkX+XRQm16eZLqLNS8RSZXZw==",
          "optional": true,
          "requires": {
            "ms": "^2.1.1"
          }
        }
      }
    },
    "rimraf": {
      "version": "2.6.3",
      "resolved": "https://registry.npmjs.org/rimraf/-/rimraf-2.6.3.tgz",
      "integrity": "sha512-mwqeW5XsA2qAejG46gYdENaxXjx9onRNCfn7L0duuP4hCuTIi/QO7PDK07KJfp1d+izWPrzEJDcSqBa0OZQriA==",
      "dev": true,
      "requires": {
        "glob": "^7.1.3"
      }
    },
    "run-async": {
      "version": "2.3.0",
      "resolved": "https://registry.npmjs.org/run-async/-/run-async-2.3.0.tgz",
      "integrity": "sha1-A3GrSuC91yDUFm19/aZP96RFpsA=",
      "dev": true,
      "requires": {
        "is-promise": "^2.1.0"
      }
    },
    "rxjs": {
      "version": "6.5.3",
      "resolved": "https://registry.npmjs.org/rxjs/-/rxjs-6.5.3.tgz",
      "integrity": "sha512-wuYsAYYFdWTAnAaPoKGNhfpWwKZbJW+HgAJ+mImp+Epl7BG8oNWBCTyRM8gba9k4lk8BgWdoYm21Mo/RYhhbgA==",
      "dev": true,
      "requires": {
        "tslib": "^1.9.0"
      }
    },
    "safe-buffer": {
      "version": "5.2.0",
      "resolved": "https://registry.npmjs.org/safe-buffer/-/safe-buffer-5.2.0.tgz",
      "integrity": "sha512-fZEwUGbVl7kouZs1jCdMLdt95hdIv0ZeHg6L7qPeciMZhZ+/gdesW4wgTARkrFWEpspjEATAzUGPG8N2jJiwbg=="
    },
    "safer-buffer": {
      "version": "2.1.2",
      "resolved": "https://registry.npmjs.org/safer-buffer/-/safer-buffer-2.1.2.tgz",
      "integrity": "sha512-YZo3K82SD7Riyi0E1EQPojLz7kpepnSQI9IyPbHHg1XXXevb5dJI7tpyN2ADxGcQbHG7vcyRHk0cbwqcQriUtg=="
    },
    "semver": {
      "version": "6.3.0",
      "resolved": "https://registry.npmjs.org/semver/-/semver-6.3.0.tgz",
      "integrity": "sha512-b39TBaTSfV6yBrapU89p5fKekE2m/NwnDocOVruQFS1/veMgdzuPcnOM34M6CwxW8jH/lxEa5rBoDeUwu5HHTw==",
      "optional": true
    },
    "send": {
      "version": "0.17.1",
      "resolved": "https://registry.npmjs.org/send/-/send-0.17.1.tgz",
      "integrity": "sha512-BsVKsiGcQMFwT8UxypobUKyv7irCNRHk1T0G680vk88yf6LBByGcZJOTJCrTP2xVN6yI+XjPJcNuE3V4fT9sAg==",
      "requires": {
        "debug": "2.6.9",
        "depd": "~1.1.2",
        "destroy": "~1.0.4",
        "encodeurl": "~1.0.2",
        "escape-html": "~1.0.3",
        "etag": "~1.8.1",
        "fresh": "0.5.2",
        "http-errors": "~1.7.2",
        "mime": "1.6.0",
        "ms": "2.1.1",
        "on-finished": "~2.3.0",
        "range-parser": "~1.2.1",
        "statuses": "~1.5.0"
      },
      "dependencies": {
        "debug": {
          "version": "2.6.9",
          "resolved": "https://registry.npmjs.org/debug/-/debug-2.6.9.tgz",
          "integrity": "sha512-bC7ElrdJaJnPbAP+1EotYvqZsb3ecl5wi6Bfi6BJTUcNowp6cvspg0jXznRTKDjm/E7AdgFBVeAPVMNcKGsHMA==",
          "requires": {
            "ms": "2.0.0"
          },
          "dependencies": {
            "ms": {
              "version": "2.0.0",
              "resolved": "https://registry.npmjs.org/ms/-/ms-2.0.0.tgz",
              "integrity": "sha1-VgiurfwAvmwpAd9fmGF4jeDVl8g="
            }
          }
        },
        "mime": {
          "version": "1.6.0",
          "resolved": "https://registry.npmjs.org/mime/-/mime-1.6.0.tgz",
          "integrity": "sha512-x0Vn8spI+wuJ1O6S7gnbaQg8Pxh4NNHb7KSINmEWKiPE4RKOplvijn+NkmYmmRgP68mc70j2EbeTFRsrswaQeg=="
        },
        "ms": {
          "version": "2.1.1",
          "resolved": "https://registry.npmjs.org/ms/-/ms-2.1.1.tgz",
          "integrity": "sha512-tgp+dl5cGk28utYktBsrFqA7HKgrhgPsg6Z/EfhWI4gl1Hwq8B/GmY/0oXZ6nF8hDVesS/FpnYaD/kOWhYQvyg=="
        }
      }
    },
    "serve-static": {
      "version": "1.14.1",
      "resolved": "https://registry.npmjs.org/serve-static/-/serve-static-1.14.1.tgz",
      "integrity": "sha512-JMrvUwE54emCYWlTI+hGrGv5I8dEwmco/00EvkzIIsR7MqrHonbD9pO2MOfFnpFntl7ecpZs+3mW+XbQZu9QCg==",
      "requires": {
        "encodeurl": "~1.0.2",
        "escape-html": "~1.0.3",
        "parseurl": "~1.3.3",
        "send": "0.17.1"
      }
    },
    "setprototypeof": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/setprototypeof/-/setprototypeof-1.1.1.tgz",
      "integrity": "sha512-JvdAWfbXeIGaZ9cILp38HntZSFSo3mWg6xGcJJsd+d4aRMOqauag1C63dJfDw7OaMYwEbHMOxEZ1lqVRYP2OAw=="
    },
    "shebang-command": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/shebang-command/-/shebang-command-1.2.0.tgz",
      "integrity": "sha1-RKrGW2lbAzmJaMOfNj/uXer98eo=",
      "dev": true,
      "requires": {
        "shebang-regex": "^1.0.0"
      }
    },
    "shebang-regex": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/shebang-regex/-/shebang-regex-1.0.0.tgz",
      "integrity": "sha1-2kL0l0DAtC2yypcoVxyxkMmO/qM=",
      "dev": true
    },
    "signal-exit": {
      "version": "3.0.2",
      "resolved": "https://registry.npmjs.org/signal-exit/-/signal-exit-3.0.2.tgz",
      "integrity": "sha1-tf3AjxKH6hF4Yo5BXiUTK3NkbG0="
    },
    "slice-ansi": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/slice-ansi/-/slice-ansi-2.1.0.tgz",
      "integrity": "sha512-Qu+VC3EwYLldKa1fCxuuvULvSJOKEgk9pi8dZeCVK7TqBfUNTH4sFkk4joj8afVSfAYgJoSOetjx9QWOJ5mYoQ==",
      "dev": true,
      "requires": {
        "ansi-styles": "^3.2.0",
        "astral-regex": "^1.0.0",
        "is-fullwidth-code-point": "^2.0.0"
      }
    },
    "snakeize": {
      "version": "0.1.0",
      "resolved": "https://registry.npmjs.org/snakeize/-/snakeize-0.1.0.tgz",
      "integrity": "sha1-EMCI2LWOsHazIpu1oE4jLOEmQi0=",
      "optional": true
    },
    "sprintf-js": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/sprintf-js/-/sprintf-js-1.0.3.tgz",
      "integrity": "sha1-BOaSb2YolTVPPdAVIDYzuFcpfiw=",
      "dev": true
    },
    "statuses": {
      "version": "1.5.0",
      "resolved": "https://registry.npmjs.org/statuses/-/statuses-1.5.0.tgz",
      "integrity": "sha1-Fhx9rBd2Wf2YEfQ3cfqZOBR4Yow="
    },
    "stream-events": {
      "version": "1.0.5",
      "resolved": "https://registry.npmjs.org/stream-events/-/stream-events-1.0.5.tgz",
      "integrity": "sha512-E1GUzBSgvct8Jsb3v2X15pjzN1tYebtbLaMg+eBOUOAxgbLoSbT2NS91ckc5lJD1KfLjId+jXJRgo0qnV5Nerg==",
      "optional": true,
      "requires": {
        "stubs": "^3.0.0"
      }
    },
    "stream-shift": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/stream-shift/-/stream-shift-1.0.0.tgz",
      "integrity": "sha1-1cdSgl5TZ+eG944Y5EXqIjoVWVI=",
      "optional": true
    },
    "streamsearch": {
      "version": "0.1.2",
      "resolved": "https://registry.npmjs.org/streamsearch/-/streamsearch-0.1.2.tgz",
      "integrity": "sha1-gIudDlb8Jz2Am6VzOOkpkZoanxo="
    },
    "string-width": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/string-width/-/string-width-2.1.1.tgz",
      "integrity": "sha512-nOqH59deCq9SRHlxq1Aw85Jnt4w6KvLKqWVik6oA9ZklXLNIOlqg4F2yrT1MVaTjAqvVwdfeZ7w7aCvJD7ugkw==",
      "dev": true,
      "requires": {
        "is-fullwidth-code-point": "^2.0.0",
        "strip-ansi": "^4.0.0"
      }
    },
    "string_decoder": {
      "version": "0.10.31",
      "resolved": "https://registry.npmjs.org/string_decoder/-/string_decoder-0.10.31.tgz",
      "integrity": "sha1-YuIDvEF2bGwoyfyEMB2rHFMQ+pQ=",
      "optional": true
    },
    "strip-ansi": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/strip-ansi/-/strip-ansi-4.0.0.tgz",
      "integrity": "sha1-qEeQIusaw2iocTibY1JixQXuNo8=",
      "dev": true,
      "requires": {
        "ansi-regex": "^3.0.0"
      }
    },
    "strip-json-comments": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/strip-json-comments/-/strip-json-comments-2.0.1.tgz",
      "integrity": "sha1-PFMZQukIwml8DsNEhYwobHygpgo=",
      "dev": true
    },
    "stubs": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/stubs/-/stubs-3.0.0.tgz",
      "integrity": "sha1-6NK6H6nJBXAwPAMLaQD31fiavls=",
      "optional": true
    },
    "supports-color": {
      "version": "5.5.0",
      "resolved": "https://registry.npmjs.org/supports-color/-/supports-color-5.5.0.tgz",
      "integrity": "sha512-QjVjwdXIt408MIiAqCX4oUKsgU2EqAGzs2Ppkm4aQYbjm+ZEWEcW4SfFNTr4uMNZma0ey4f5lgLrkB0aX0QMow==",
      "dev": true,
      "requires": {
        "has-flag": "^3.0.0"
      }
    },
    "table": {
      "version": "5.4.6",
      "resolved": "https://registry.npmjs.org/table/-/table-5.4.6.tgz",
      "integrity": "sha512-wmEc8m4fjnob4gt5riFRtTu/6+4rSe12TpAELNSqHMfF3IqnA+CH37USM6/YR3qRZv7e56kAEAtd6nKZaxe0Ug==",
      "dev": true,
      "requires": {
        "ajv": "^6.10.2",
        "lodash": "^4.17.14",
        "slice-ansi": "^2.1.0",
        "string-width": "^3.0.0"
      },
      "dependencies": {
        "ansi-regex": {
          "version": "4.1.0",
          "resolved": "https://registry.npmjs.org/ansi-regex/-/ansi-regex-4.1.0.tgz",
          "integrity": "sha512-1apePfXM1UOSqw0o9IiFAovVz9M5S1Dg+4TrDwfMewQ6p/rmMueb7tWZjQ1rx4Loy1ArBggoqGpfqqdI4rondg==",
          "dev": true
        },
        "string-width": {
          "version": "3.1.0",
          "resolved": "https://registry.npmjs.org/string-width/-/string-width-3.1.0.tgz",
          "integrity": "sha512-vafcv6KjVZKSgz06oM/H6GDBrAtz8vdhQakGjFIvNrHA6y3HCF1CInLy+QLq8dTJPQ1b+KDUqDFctkdRW44e1w==",
          "dev": true,
          "requires": {
            "emoji-regex": "^7.0.1",
            "is-fullwidth-code-point": "^2.0.0",
            "strip-ansi": "^5.1.0"
          }
        },
        "strip-ansi": {
          "version": "5.2.0",
          "resolved": "https://registry.npmjs.org/strip-ansi/-/strip-ansi-5.2.0.tgz",
          "integrity": "sha512-DuRs1gKbBqsMKIZlrffwlug8MHkcnpjs5VPmL1PAh+mA30U0DTotfDZ0d2UUsXpPmPmMMJ6W773MaA3J+lbiWA==",
          "dev": true,
          "requires": {
            "ansi-regex": "^4.1.0"
          }
        }
      }
    },
    "teeny-request": {
      "version": "5.3.0",
      "resolved": "https://registry.npmjs.org/teeny-request/-/teeny-request-5.3.0.tgz",
      "integrity": "sha512-sN9E3JvEBe2CFqB/jpJpw1erWD1C7MxyYCxogHFCQSyZfkHYcdf4wzVQSw7FZxbwcfnS+FP0W9BS0mp6SEOKjg==",
      "optional": true,
      "requires": {
        "http-proxy-agent": "^2.1.0",
        "https-proxy-agent": "^3.0.0",
        "node-fetch": "^2.2.0",
        "stream-events": "^1.0.5",
        "uuid": "^3.3.2"
      },
      "dependencies": {
        "https-proxy-agent": {
          "version": "3.0.0",
          "resolved": "https://registry.npmjs.org/https-proxy-agent/-/https-proxy-agent-3.0.0.tgz",
          "integrity": "sha512-y4jAxNEihqvBI5F3SaO2rtsjIOnnNA8sEbuiP+UhJZJHeM2NRm6c09ax2tgqme+SgUUvjao2fJXF4h3D6Cb2HQ==",
          "optional": true,
          "requires": {
            "agent-base": "^4.3.0",
            "debug": "^3.1.0"
          }
        }
      }
    },
    "text-table": {
      "version": "0.2.0",
      "resolved": "https://registry.npmjs.org/text-table/-/text-table-0.2.0.tgz",
      "integrity": "sha1-f17oI66AUgfACvLfSoTsP8+lcLQ=",
      "dev": true
    },
    "through": {
      "version": "2.3.8",
      "resolved": "https://registry.npmjs.org/through/-/through-2.3.8.tgz",
      "integrity": "sha1-DdTJ/6q8NXlgsbckEV1+Doai4fU=",
      "dev": true
    },
    "through2": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/through2/-/through2-3.0.1.tgz",
      "integrity": "sha512-M96dvTalPT3YbYLaKaCuwu+j06D/8Jfib0o/PxbVt6Amhv3dUAtW6rTV1jPgJSBG83I/e04Y6xkVdVhSRhi0ww==",
      "optional": true,
      "requires": {
        "readable-stream": "2 || 3"
      },
      "dependencies": {
        "readable-stream": {
          "version": "3.4.0",
          "resolved": "https://registry.npmjs.org/readable-stream/-/readable-stream-3.4.0.tgz",
          "integrity": "sha512-jItXPLmrSR8jmTRmRWJXCnGJsfy85mB3Wd/uINMXA65yrnFo0cPClFIUWzo2najVNSl+mx7/4W8ttlLWJe99pQ==",
          "optional": true,
          "requires": {
            "inherits": "^2.0.3",
            "string_decoder": "^1.1.1",
            "util-deprecate": "^1.0.1"
          }
        },
        "string_decoder": {
          "version": "1.3.0",
          "resolved": "https://registry.npmjs.org/string_decoder/-/string_decoder-1.3.0.tgz",
          "integrity": "sha512-hkRX8U1WjJFd8LsDJ2yQ/wWWxaopEsABU1XfkM8A+j0+85JAGppt16cr1Whg6KIbb4okU6Mql6BOj+uup/wKeA==",
          "optional": true,
          "requires": {
            "safe-buffer": "~5.2.0"
          }
        }
      }
    },
    "tmp": {
      "version": "0.0.33",
      "resolved": "https://registry.npmjs.org/tmp/-/tmp-0.0.33.tgz",
      "integrity": "sha512-jRCJlojKnZ3addtTOjdIqoRuPEKBvNXcGYqzO6zWZX8KfKEpnGY5jfggJQ3EjKuu8D4bJRr0y+cYJFmYbImXGw==",
      "dev": true,
      "requires": {
        "os-tmpdir": "~1.0.2"
      }
    },
    "toidentifier": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/toidentifier/-/toidentifier-1.0.0.tgz",
      "integrity": "sha512-yaOH/Pk/VEhBWWTlhI+qXxDFXlejDGcQipMlyxda9nthulaxLZUNcUqFxokp0vcYnvteJln5FNQDRrxj3YcbVw=="
    },
    "tslib": {
      "version": "1.10.0",
      "resolved": "https://registry.npmjs.org/tslib/-/tslib-1.10.0.tgz",
      "integrity": "sha512-qOebF53frne81cf0S9B41ByenJ3/IuH8yJKngAX35CmiZySA0khhkovshKK+jGCaMnVomla7gVlIcc3EvKPbTQ=="
    },
    "type-check": {
      "version": "0.3.2",
      "resolved": "https://registry.npmjs.org/type-check/-/type-check-0.3.2.tgz",
      "integrity": "sha1-WITKtRLPHTVeP7eE8wgEsrUg23I=",
      "dev": true,
      "requires": {
        "prelude-ls": "~1.1.2"
      }
    },
    "type-is": {
      "version": "1.6.18",
      "resolved": "https://registry.npmjs.org/type-is/-/type-is-1.6.18.tgz",
      "integrity": "sha512-TkRKr9sUTxEH8MdfuCSP7VizJyzRNMjj2J2do2Jr3Kym598JVdEksuzPQCnlFPW4ky9Q+iA+ma9BGm06XQBy8g==",
      "requires": {
        "media-typer": "0.3.0",
        "mime-types": "~2.1.24"
      }
    },
    "typedarray": {
      "version": "0.0.6",
      "resolved": "https://registry.npmjs.org/typedarray/-/typedarray-0.0.6.tgz",
      "integrity": "sha1-hnrHTjhkGHsdPUfZlqeOxciDB3c=",
      "optional": true
    },
    "typedarray-to-buffer": {
      "version": "3.1.5",
      "resolved": "https://registry.npmjs.org/typedarray-to-buffer/-/typedarray-to-buffer-3.1.5.tgz",
      "integrity": "sha512-zdu8XMNEDepKKR+XYOXAVPtWui0ly0NtohUscw+UmaHiAWT8hrV1rr//H6V+0DvJ3OQ19S979M0laLfX8rm82Q==",
      "optional": true,
      "requires": {
        "is-typedarray": "^1.0.0"
      }
    },
    "unique-string": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/unique-string/-/unique-string-2.0.0.tgz",
      "integrity": "sha512-uNaeirEPvpZWSgzwsPGtU2zVSTrn/8L5q/IexZmH0eH6SA73CmAA5U4GwORTxQAZs95TAXLNqeLoPPNO5gZfWg==",
      "optional": true,
      "requires": {
        "crypto-random-string": "^2.0.0"
      }
    },
    "unpipe": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/unpipe/-/unpipe-1.0.0.tgz",
      "integrity": "sha1-sr9O6FFKrmFltIF4KdIbLvSZBOw="
    },
    "uri-js": {
      "version": "4.2.2",
      "resolved": "https://registry.npmjs.org/uri-js/-/uri-js-4.2.2.tgz",
      "integrity": "sha512-KY9Frmirql91X2Qgjry0Wd4Y+YTdrdZheS8TFwvkbLWf/G5KNJDCh6pKL5OZctEW4+0Baa5idK2ZQuELRwPznQ==",
      "dev": true,
      "requires": {
        "punycode": "^2.1.0"
      }
    },
    "util-deprecate": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/util-deprecate/-/util-deprecate-1.0.2.tgz",
      "integrity": "sha1-RQ1Nyfpw3nMnYvvS1KKJgUGaDM8=",
      "optional": true
    },
    "utils-merge": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/utils-merge/-/utils-merge-1.0.1.tgz",
      "integrity": "sha1-n5VxD1CiZ5R7LMwSR0HBAoQn5xM="
    },
    "uuid": {
      "version": "3.3.3",
      "resolved": "https://registry.npmjs.org/uuid/-/uuid-3.3.3.tgz",
      "integrity": "sha512-pW0No1RGHgzlpHJO1nsVrHKpOEIxkGg1xB+v0ZmdNH5OAeAwzAVrCnI2/6Mtx+Uys6iaylxa+D3g4j63IKKjSQ==",
      "optional": true
    },
    "vary": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/vary/-/vary-1.1.2.tgz",
      "integrity": "sha1-IpnwLG3tMNSllhsLn3RSShj2NPw="
    },
    "walkdir": {
      "version": "0.4.1",
      "resolved": "https://registry.npmjs.org/walkdir/-/walkdir-0.4.1.tgz",
      "integrity": "sha512-3eBwRyEln6E1MSzcxcVpQIhRG8Q1jLvEqRmCZqS3dsfXEDR/AhOF4d+jHg1qvDCpYaVRZjENPQyrVxAkQqxPgQ==",
      "optional": true
    },
    "websocket-driver": {
      "version": "0.7.3",
      "resolved": "https://registry.npmjs.org/websocket-driver/-/websocket-driver-0.7.3.tgz",
      "integrity": "sha512-bpxWlvbbB459Mlipc5GBzzZwhoZgGEZLuqPaR0INBGnPAY1vdBX6hPnoFXiw+3yWxDuHyQjO2oXTMyS8A5haFg==",
      "requires": {
        "http-parser-js": ">=0.4.0 <0.4.11",
        "safe-buffer": ">=5.1.0",
        "websocket-extensions": ">=0.1.1"
      }
    },
    "websocket-extensions": {
      "version": "0.1.3",
      "resolved": "https://registry.npmjs.org/websocket-extensions/-/websocket-extensions-0.1.3.tgz",
      "integrity": "sha512-nqHUnMXmBzT0w570r2JpJxfiSD1IzoI+HGVdd3aZ0yNi3ngvQ4jv1dtHt5VGxfI2yj5yqImPhOK4vmIh2xMbGg=="
    },
    "which": {
      "version": "1.3.1",
      "resolved": "https://registry.npmjs.org/which/-/which-1.3.1.tgz",
      "integrity": "sha512-HxJdYWq1MTIQbJ3nw0cqssHoTNU267KlrDuGZ1WYlxDStUtKUhOaJmh112/TZmHxxUfuJqPXSOm7tDyas0OSIQ==",
      "dev": true,
      "requires": {
        "isexe": "^2.0.0"
      }
    },
    "wordwrap": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/wordwrap/-/wordwrap-1.0.0.tgz",
      "integrity": "sha1-J1hIEIkUVqQXHI0CJkQa3pDLyus=",
      "dev": true
    },
    "wrappy": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/wrappy/-/wrappy-1.0.2.tgz",
      "integrity": "sha1-tSQ9jz7BqjXxNkYFvA0QNuMKtp8="
    },
    "write": {
      "version": "1.0.3",
      "resolved": "https://registry.npmjs.org/write/-/write-1.0.3.tgz",
      "integrity": "sha512-/lg70HAjtkUgWPVZhZcm+T4hkL8Zbtp1nFNOn3lRrxnlv50SRBv7cR7RqR+GMsd3hUXy9hWBo4CHTbFTcOYwig==",
      "dev": true,
      "requires": {
        "mkdirp": "^0.5.1"
      }
    },
    "write-file-atomic": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/write-file-atomic/-/write-file-atomic-3.0.0.tgz",
      "integrity": "sha512-EIgkf60l2oWsffja2Sf2AL384dx328c0B+cIYPTQq5q2rOYuDV00/iPFBOUiDKKwKMOhkymH8AidPaRvzfxY+Q==",
      "optional": true,
      "requires": {
        "imurmurhash": "^0.1.4",
        "is-typedarray": "^1.0.0",
        "signal-exit": "^3.0.2",
        "typedarray-to-buffer": "^3.1.5"
      }
    },
    "xdg-basedir": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/xdg-basedir/-/xdg-basedir-4.0.0.tgz",
      "integrity": "sha512-PSNhEJDejZYV7h50BohL09Er9VaIefr2LMAf3OEmpCkjOi34eYyQYAXUTjEQtZJTKcF0E2UKTh+osDLsgNim9Q==",
      "optional": true
    },
    "xtend": {
      "version": "4.0.2",
      "resolved": "https://registry.npmjs.org/xtend/-/xtend-4.0.2.tgz",
      "integrity": "sha512-LKYU1iAXJXUgAXn9URjiu+MWhyUXHsvfp7mcuYm9dSUKK0/CjtrUwFAxD82/mCWbtLsGjFIad0wIsod4zrTAEQ=="
    },
    "yallist": {
      "version": "3.1.1",
      "resolved": "https://registry.npmjs.org/yallist/-/yallist-3.1.1.tgz",
      "integrity": "sha512-a4UGQaWPH59mOXUYnAG2ewncQS4i4F43Tv3JoAM+s2VDAmS9NsK8GpDMLrCHPksFT7h3K6TOoUNn2pb7RoXx4g==",
      "optional": true
    }
  }
}
