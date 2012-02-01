# GeoPipe

GeoPipe is an attempt by [Sidelab](http://www.sidelab.com/) to create a practial framework for wiring various geospatial components together in a lightweight way. While we recognize that there is some [excellent standards work](http://www.opengeospatial.org/) going on in with regards in the GIS solution space, wiring components together using existing standards for simple solutions is definitely overkill.

The GeoPipe project is an attempt to create discrete and composable components that are responsible for a single operation in a Geospatial stack.  Our current thinking on components is described below:

## Localizer

The purpose of a localizer is to guess potential locales given some input text.  It's primary purpose should be on guessing free-text addresses but more generic text should be supported to.

IN:

```json
{
    "items": ["Item One", "Item Two"]
}
```

OUT:

```json
{
    "items": [{
        "text": "Item One",
        "locales": ["EN"]
    }, {
        "text": "Item Two",
        "locales": ["EN"]
    }]
}
```

## Address Parser

An address parser can take locale specific text and parse the address according to the rules of the locale.

IN:

```json
{
    "items": [{
        "text": "1 Queen St, Brisbane",
        "locales": ["EN-AU"]
    }]
}
```

OUT:

```json
{
    "items": [{
        "text": "1 Queen St, Brisbane",
        "locales": ["EN-AU"],
        "address": {
            
        }
    }]
}
```

## Address Normalizer

To be completed.

## Locator

A locator component takes in a [ECQL](http://docs.codehaus.org/display/GEOTOOLS/ECQL+Parser+Design) filter and return a list of geospatial objects that fulfil the filter conditions.

## Collator / Sorter

To be completed.

## Router

To be completed.

