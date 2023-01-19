## Entity Relation Diagram builder

This tool aims to generate an entity relation diagram from the database of a working GLPI instance.

## Usage

Copy the .php file in glpi/tools/ directory then run it

```php tools/builddatabaseschema.php > /tmp/diagram.txt```

The output is text data for PlantUML.

To generate the textual representation of the diagram for a plugin only, just specify the plugin's internal name (its folder name).

```php tools/builddatabaseschema.php formcreator > /tmp/diagram.txt```
```php tools/builddatabaseschema.php genericobject > /tmp/diagram.txt```

## Supported renderers

The code can also handle mermaid and graphviz. Mermaid fails to generate an image when using the tables of GLPI because of too many objects to draw.

Graphviz works but requires some more work to get a nice result.

PlantUML uses Graphviz internally and gives a good result with less efforts.

To use an other renderer, the generator instanciation must be changed accordying to your preferred rendering engine.

## Generating a picture from the PlantUML renderer

To transform the PlantUML output into a picture use the following command

```plantuml -Tsvg input.txt```

A .svg file with the name of the input file name will be generated. Open it with a browser.

## Limitations

The final image is not fully readable when generating GLPI core schema. It should be sufficient for plugins.
