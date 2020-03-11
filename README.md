## 2020-03-09 JS And Angular Exercises

#### Functions

/

#### Scope & Closure

Exercises:

- [https://davidvangompel.typeform.com/to/Hxr1WD](https://davidvangompel.typeform.com/to/Hxr1WD)

Resources:

- [https://tylermcginnis.com/javascript-visualizer/](https://tylermcginnis.com/javascript-visualizer/)

#### ES6

Exercises:

- [Declarative programming](https://codesandbox.io/s/declarative-programming-exercises-plslr)
- [General ES6 exercises](https://codesandbox.io/s/es6-exercises-0kjyk)

Resources:

- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

#### Async

Exercises:

- [Battleship: CLI](https://codesandbox.io/s/battleship-cli-pfgwx)
- [(Battleship: api)](https://codesandbox.io/s/battleship-api-vwuih)

#### TypeScript

Exercises:

- [TypeScript exercises](https://codesandbox.io/s/typescript-exercises-iv4ns)

#### Angular

We're going to make a Movie Watchlist application. The application authenticates with [The Mobie DB](https://developers.themoviedb.org/4/auth/user-authorization-1), and [fetches all latest movies](https://developers.themoviedb.org/3/movies/get-top-rated-movies) after logging in.
The authenticated user can add Movies to his watchlist, which is [stored at The Movie DB](https://developers.themoviedb.org/3/lists/v4-or-v3-lists) in a custom list.

1. Setup

   - Create a new Angular project (with SCSS). [https://cli.angular.io/](https://cli.angular.io/)
   - Add Angular Material. [https://material.angular.io/](https://material.angular.io/)
   - You can find all code for the App component [here at Codesandbox](https://codesandbox.io/s/angular-exercise-start-0b6oy)

2. Databinding & Directives

   - Render all movies in a list
   - Note: Movie posters can be retrieved with the following path: `http://image.tmdb.org/t/p/w185/MOVIE_POSTER_PATH`
   - You can use the following code as a reference:

   ```Html
    <li class="movie-list__item">
        <mat-card class="mat-elevation-z1 movie-card">
          <img
            class="mat-elevation-z14 movie-card__img"
            mat-card-image
            src="POSTER_PATH"
            alt="MOVIE_TITLE"
          />
          <mat-card-subtitle>
            (MEDIA_TYPE)
            GENRES
          </mat-card-subtitle>
          <mat-card-title>MOVIE_TITLE</mat-card-title>
          <mat-card-content class="movie-card__content">
            <time dateTime="RELEASE_DATE"
              >RELEASE_DATE</time
            >
            <span class="vote">
              <mat-icon>star</mat-icon><span>VOTE_AVERAGE</span>
            </span>
          </mat-card-content>
          <button
            mat-mini-fab
            color="primary"
            class="movie-card__fav"
          >
            <mat-icon>bookmark</mat-icon>
          </button>
        </mat-card>
      </li>
   ```

3. Basic App.component.ts features:

   - Implement `get distinctGenres()`.
     - Render these distinct genres in the sidebar in App.component.ts
   - Create an `addToWatchlist` method, which adds a movie to the watchlist when clicking the bookmark icon.
   - Implement `get watchlist()`
     - Render the watchlist in the sidebar

```html
<li class="watchlist__movies__item">
  <div class="watchlist__movies__item__img">
    <img src="POSTER_PATH" alt="MOVIE_TITLE" />
  </div>
  <div class="watchlist__movies__item__info mat-h4">
    <h4 class="watchlist__movies__item__title">
      MOVIE_TITLE
    </h4>
    <p class="watchlist__movies__item__genre">
      GENRES
    </p>
  </div>
  <div class="watchlist__movies__item__score">
    <span class="vote">
      <mat-icon>star</mat-icon><span>VOTE_AVERAGE</span>
    </span>
  </div>
</li>
```

4. Modules & Components

   - Split the App component into logical modules and components
   - Make sure everything keeps working!

5. Custom pipe

   - Create a pipe "poster" which automatically prefixes a movie poster path with the poster URL `http://image.tmdb.org/t/p/w185/`
   - The pipe should accept the width of the image you want te render, usage: `<img [src]="movie.poster_path | poster:200"`
