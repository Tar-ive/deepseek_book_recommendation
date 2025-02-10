# My Girlfriend's Book Recommendation System

I built this system to find books that my girlfriend might enjoy based on her current favorites. It combines data from Goodreads with AI analysis to suggest books that match her specific taste in literature.

## Her Reading Preferences

Her favorite books include:
- "White Nights" by Dostoevsky (psychological realism)
- "Pride and Prejudice" by Austen (classic literature)
- "The Metamorphosis" by Kafka (surrealism)
- "Harry Potter and the Prisoner of Azkaban" by Rowling (fantasy)
- "The Picture of Dorian Gray" by Wilde (philosophical fiction)
- "Notes from Underground" by Dostoevsky (existentialism)

## How It Works

The system works in three steps to find books she might like:

1. **Finding Similar Readers**
   - Looks through Goodreads data to find readers who liked the same books
   - Identifies what other books these similar readers enjoyed

2. **Filtering Recommendations**
   - Focuses on books with high ratings
   - Removes books with too few reviews
   - Excludes books she's already read

3. **AI Analysis**
   - Uses DeepSeek's AI to analyze each recommended book
   - Compares writing styles and themes to her favorites
   - Ranks books based on how well they match her taste

## Setting Up

1. **Install Required Packages**
   ```python
   !pip install openai pandas numpy scikit-learn scipy
   ```

2. **Set Up API Access**
   ```python
   from google.colab import userdata
   userdata.set('DEEPSEEK_API_KEY', 'your-api-key-here')
   ```

3. **Prepare Data**
   - Download the Goodreads dataset
   - Run the notebook to process the data

## Using the System

1. **Update Reading List**
   ```python
   # Her current favorite books
   core_books = [
       ('White Nights', '1772910', 5),
       ('Pride and Prejudice', '14918', 5),
       ('The Metamorphosis', '7718', 5),
       ('Harry Potter and the Prisoner of Azkaban', '464164', 5),
       ('The Picture of Dorian Gray', '87809', 5),
       ('Notes from Underground', '49455', 5)
   ]
   ```

2. **Get Recommendations**
   ```python
   # Generate and rank recommendations
   recommendations = generate_recommendations(core_books)
   ```

## What You Get

For each recommended book, you'll see:
- Title and author
- How similar it is to her favorites
- Why the AI thinks she'll like it
- Link to Goodreads page
- Book cover image

## Current Limitations

- Sometimes takes a while to process all books
- Works better with well-known books
- AI responses can be inconsistent
- Needs a DeepSeek API key

## Future Plans

Planning to add:
- Faster processing
- Genre filters
- Better error handling
- Support for multiple reading lists
- Save previous recommendations

## Need Help?

If you want to use this for your own book recommendations or have suggestions for improvements, feel free to:
- Open an issue
- Submit a pull request
- Contact me for questions

## Required Packages
```
pandas
numpy
scikit-learn
scipy
openai
```

## Data Source
Uses the Goodreads books dataset for all book information and user ratings.
