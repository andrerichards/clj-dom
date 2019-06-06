# clj-dom

Basic Clojure wrapper for JDOM 2

## Usage

[Maven](http://maven.apache.org/) dependency information:
```xml
    <dependency>
      <groupId>defng</groupId>
      <artifactId>clj-dom</artifactId>
      <version>1.3.0</version>
    </dependency>
```

```
(require '[defng.clj-dom.core :as dom])

(def xml (dom/parse-str "<e1>\n  <e2 name=\"n2.1\">t2.1</e2>\n  <e2 name=\"n2.2\">t2.2</e2>\n</e1>"))
=> #'user/xml

(dom/find-first xml "e2")
=> #object[org.jdom2.Element 0x6138dafd "[Element: <e2/>]"]

(dom/find-all xml "e2")
=> [#object[org.jdom2.Element 0x6138dafd "[Element: <e2/>]"] #object[org.jdom2.Element 0x38c0d3e9 "[Element: <e2/>]"]]

(dom/get-value xml "e2/@name")
=> "n2.1"

```

Namespaces are supported:

```
(import org.jdom2.Namespace)
=> org.jdom2.Namespace

(def xml (dom/parse-str "<e1 xmlns=\"http://yournamespace.org\">\n  <e2 name=\"n2.1\">t2.1</e2>\n  <e2 name=\"n2.2\">t2.2</e2>\n</e1>"))
=> #'user/xml

(def namespaces
  [(Namespace/getNamespace "ns" "http://yournamespace.org")])
=> #'user/namespaces

(dom/get-value xml "ns:e2/@name" namespaces)
=> "n2.1"
```

## License

Copyright © 2017 Andre Richards

Licensed under Eclipse Public License (see [LICENSE](LICENSE)).