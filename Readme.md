## Makefile Recursive Call Sub Makefile

```
$(MAKE) -C $PATH
```

```
ref: https://www.gnu.org/software/make/manual/html_node/Recursion.html
```

#### Makefile Wildcard Check if object existed?

- Ref: https://www.gnu.org/software/make/manual/html_node/Wildcard-Function.html

```
../node_modules:
	@cd .. && npm install

../app/components:
	@cd .. && ./node_modules/bower/bin/bower install

prepare: $(wildcard platforms/*) $(wildcard plugins/*) ../node_modules ../app/components
	@../node_modules/cordova/bin/cordova prepare

clean:
	@rm -rf platforms/*
	@rm -rf plugins/*

lift: prepare
	@../node_modules/cordova/bin/cordova run
```
