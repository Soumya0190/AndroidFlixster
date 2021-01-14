# P.S. The Code is Pushed to Master Branch, not Main Branch

# Flix
Flix is an app that allows users to browse movies from the [The Movie Database API](http://docs.themoviedb.apiary.io/#).

📝 AsyncHttpClient Network Request Snippet
```Java
import com.codepath.asynchttpclient.AsyncHttpClient;

AsyncHttpClient client = new AsyncHttpClient();
RequestParams params = new RequestParams();
params.put("limit", "5");
params.put("page", 0);
client.get("https://api.thecatapi.com/v1/images/search", params, new TextHttpResponseHandler() {
        @Override
        public void onSuccess(int statusCode, Headers headers, String response) {
            // called when response HTTP status is "200 OK"
        }

        @Override
        public void onFailure(int statusCode, Headers headers, String errorResponse, Throwable t) {
            // called when response HTTP status is "4XX" (eg. 401, 403, 404)
        }	
    }
);
```

## Flix Part 1

### User Stories

#### REQUIRED (10pts)
- [x] (10pts) User can view a list of movies (title, poster image, and overview) currently playing in theaters from the Movie Database API.

#### BONUS
- [ ] (2pts) Views should be responsive for both landscape/portrait mode.
   - [ ] (1pt) In portrait mode, the poster image, title, and movie overview is shown.
   - [ ] (1pt) In landscape mode, the rotated alternate layout should use the backdrop image instead and show the title and movie overview to the right of it.

- [ ] (2pts) Display a nice default [placeholder graphic](https://guides.codepath.org/android/Displaying-Images-with-the-Glide-Library#advanced-usage) for each image during loading
- [ ] (2pts) Improved the user interface by experimenting with styling and coloring.
- [ ] (2pts) For popular movies (i.e. a movie voted for more than 5 stars), the full backdrop image is displayed. Otherwise, a poster image, the movie title, and overview is listed. Use Heterogenous RecyclerViews and use different ViewHolder layout files for popular movies and less popular ones.

### App Walkthough GIF
<img src="http://g.recordit.co/TlmtPjgv9n.gif" width=250><br>

### Notes
Designing of the app on Android Studio was a challenge, made the mistake of designing Image and Text View in activity_main.xml instead of in item_movie.xml

### Open-source libraries used
- [Android Async HTTP](https://github.com/codepath/CPAsyncHttpClient) - Simple asynchronous HTTP requests with JSON parsing
- [Glide](https://github.com/bumptech/glide) - Image loading and caching library for Androids
