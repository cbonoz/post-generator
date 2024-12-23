# Twitter Post Generator

This project uses OpenAI's GPT-4 and DALL-E models to generate tweets and corresponding images based on current events.

## Setup

1. Clone the repository:
    ```bash
    git clone <repository-url>
    cd generate-post
    ```

2. Create a virtual environment and activate it:
    ```bash
    python3 -m venv env
    source env/bin/activate
    ```

3. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

4. Create a `.env` file in the root directory and add your OpenAI and News API keys:
    ```plaintext
    OPENAI_API_KEY=your_openai_api_key # https://openai.com/api/pricing/
    NEWS_API_KEY=your_news_api_key # https://newsapi.org/pricing
    ```

## Usage

### Generate a Tweet

The `PostGenerator` class can be used to generate tweets based on user background, target audience, and current events.

```python

background = "software, engineering, science, entrepreneurship"
target_audience = "developers, entrepreneurs"
theme = "technology, science, controversial"

current_events = get_current_events(theme)
event = current_events[0]  # or select a random event

generator = PostGenerator()
tweet = generator.generate_tweet(background, target_audience, event)
print('Generated Tweet:\n', tweet)
```

### Generate an Image from a Post

You can also generate an image based on the generated tweet.

```python
image_response = generator.generate_image_from_post(tweet)
print(image_response)
```

### Save Tweet and Image

Save the generated tweet and image to the output directory.

```python
generator.save_tweet_and_image(tweet, image_response)
```

### Rate and Improve a Tweet

You can rate the effectiveness of a tweet and get suggestions for improvement.

```python
rating = generator.rate_tweet(tweet)
print('Rating and Suggestions:\n', rating)

improved_tweet = generator.improve_tweet(tweet, rating)
print('Improved Tweet:\n', improved_tweet)
```

### Fetch Current Events

Fetch current events based on a theme.

```python
events = get_current_events("technology")
print('Current Events:\n', events)
```

## Example Notebook

Refer to the `twitter.ipynb` notebook for a complete example of generating and saving tweets and images.

## License

This project is licensed under the MIT License.
