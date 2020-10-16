# MarkdownToAsciidoc
Test project for markdown to asciidoc conversion

Also see [Here](https://matthewsetter.com/technical-documentation/asciidoc/convert-markdown-to-asciidoc-with-kramdoc/).

## Sample markdown

Downloaded from `https://www.dropbox.com/s/4z6kot27jmikhx5/forapp-markdown-sample.md`.



## Pandoc Command



```
pandoc -o sample_pandoc.adoc sample.md
```

## Docker-Asciidoctor Command

```
wsl docker run --rm -v $(pwd):/documents/ asciidoctor/docker-asciidoctor kramdoc  --wrap=ventilate --format=GFM sample.md
```

## adoc to html command

- option
  - left toc
  - data-uri
  - asciidoctor-diagram

```
wsl docker run --rm -v $(pwd):/documents/ asciidoctor/docker-asciidoctor asciidoctor <sample.adoc> -r asciidoctor-diagram -a allow-uri-read -a data-uri -a toc=left
```


# Known Problems

- 画像貼り付けが怪しい？
- ![うきっ！](http://mkb.salchu.net/image/salchu_image02.jpg "salchu_image02.jpg")

エラーが出る…

```
/usr/lib/ruby/gems/2.7.0/gems/kramdown-asciidoc-1.0.1/lib/kramdown-asciidoc/converter.rb:99:in `convert': undefined method `convert_xml_pi' for #<Kramdown::AsciiDoc::Converter:0x0000561a13adec28> (NoMethodError)
Did you mean?  convert_li
```