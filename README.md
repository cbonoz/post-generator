# Twitter Post Generator

This project generates formatted tweets based on user background, interests, target audience, and current events using OpenAI's GPT-4 model.

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
    OPENAI_API_KEY=your_openai_api_key
    NEWS_API_KEY=your_news_api_key
    ```

## Usage

1. Open the Jupyter notebook:
    ```bash
    jupyter notebook twitter.ipynb
    ```

2. Follow the instructions in the notebook to generate tweets.

## Example

Here's an example of how to use the `PostGenerator` class to generate a tweet:

```python
from openai import OpenAI
import os
from dotenv import load_dotenv
import requests

load_dotenv()

CHAT_MODEL = 'gpt-4o-mini'

class PostGenerator:
    # ...existing code...

    def generate_tweet(self, user_background, user_interests, target_audience, current_events):
        # ...existing code...

def format_article(a):
    # ...existing code...

def get_current_events(theme):
    # ...existing code...

background = "software, engineering, science, business. Worked at a startup three years as a head of engineering and at larger companies as a software engineer."
interests = "coding, open-source projects, hackathons, and startups"
target_audience = "developers and entrepreneurs"
theme = "technology, science, controversial"

current_events = get_current_events(theme)
post_generator = PostGenerator()
tweet = post_generator.generate_tweet(background, interests, target_audience, current_events)
print(tweet)
```

## License

This project is licensed under the MIT License.
