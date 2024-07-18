class EmptyTextException(Exception):
    """Custom exception for empty text input."""
    def _init_(self, message="Input text is empty. Please provide valid text."):
        self.message = message
        super()._init_(self.message)

def count_words(text):
    """Counts the number of words in the given text."""
    if not text:
        raise EmptyTextException()

    words = text.split()
    word_count = len(words)
    return word_count

# Example usage
try:
    input_text = input("Enter text: ")
    print(f"Word count: {count_words(input_text)}")
except EmptyTextException as e:
    print(e)
