# JSON Nominations

For folks interested in film and cinema who also have some technical skills, this is every Oscar nomination ever, formatted as consistent machine-readable JSON. Use it as a clean data set to answer whatever burning movie awards questions you have.

## Usage

Download the [oscar-nominations.json](./oscar-nominations.json) file and load it into your programming language or text editor of choice. Perform whatever searches or transformations you need from there.

## Schema

The file is one giant array of objects which each represent a single nomination. The objects follow a consistent schema.

```json
  {
    "category": "Best Actress",
    "year": "2023",
    "nominees": [
      "Emma Stone"
    ],
    "movies": [
      {
        "title": "Poor Things",
        "tmdb_id": 792307,
        "imdb_id": "tt14230458"
      }
    ],
    "won": true
  }
```

**Properties:**

- _category_ - The name of the category the nomination was for.
- _year_ - The year of the nomination. Note that for the first five Oscar ceremonies, the awards straddled a year and are written with a slash (e.g. "1927/28").
- _nominees_ - The names of the people, movies, or songs that were nominated. In some cases where multiple entities share a single nomination, they are listed together in this array.
- _movies_ - An array of objects representing the films the nomination was made for. Almost always a single movie, but in some rare cases one nomination was given for work in multiple films, and in _exactly one case_ a TV show was nominated instead of a movie and this array was left empty.
  * _title_ - The title of the movie.
  * _tmdb_id_ - The ID used to identify the movie in [The Movie Database's API](https://developer.themoviedb.org/docs/getting-started). This was the API used to fetch supplementary information for this JSON file. It is free and easy to use.
  * _imdb_id_ - The ID used to identify the title in IMDB's API.
- _won_ - Whether or not the nominee won the award.

## Source

The Oscars data came originally from this thorough [Oscars Winner and Nominee Master Spreadsheet](https://docs.google.com/spreadsheets/d/18P6JdOyU4Misxe66R5zMpATJBlwfmpQ_KkOOZ7ASm_c). Many thanks to the original author for putting all of this info in one place in a format I could easily parse.

From that initial source, the data was corrected and expanded through repeated trips to the API from [The Movie Database](https://developer.themoviedb.org/docs/getting-started). I also want to thank TMDB both for creating a clean usable website for movie fans, but also providing their data free of charge to developers like myself.

## Updates

If you find any issues in the JSON, feel free to [submit an issue](https://github.com/delventhalz/json-nominations/issues) or else fork the repo and [create your own PR](https://github.com/delventhalz/json-nominations/pulls). In addition to fixing typos, I would like to keep the data up to date as new nominations are made each year and perhaps expand to other awards besides the Oscars. Outside contributions towards those goals are welcome.

## License

I have [MIT licensed](./LICENSE) the JSON itself, but I don't own the Oscars, the category names, or the film names. Those all belong to their various rights holders.
