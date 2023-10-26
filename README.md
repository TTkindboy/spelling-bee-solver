# Spelling Bee Solver
```python
def is_running_on_replit():
  try:
    import replit
    return True
  except ImportError:
    return False

def clear_on_replit():
  if is_running_on_replit():
    from replit import clear
    clear()

def load_wordlist(filename):
  with open(filename, 'r') as f:
    return set(f.read().splitlines())

def find_valid_words(wordlist, letters, central_letter):
  valid_words = []
  for word in wordlist:
      if len(word) >= 4 and central_letter in word and set(word).issubset(letters):
        valid_words.append(word)
  return valid_words

def main():
  # clear_on_replit()
  wordlist = load_wordlist("words_alpha.txt")
  letters = input("Enter the 7 letters for the puzzle (no spaces): ").lower()
  central_letter = input("Enter the central letter: ").lower()
  valid_words = find_valid_words(wordlist, letters, central_letter)
  clear_on_replit()
  print("\nValid words:")
  for word in valid_words:
    print(word)

if __name__ == "__main__":
  main()
```
## Alternate method
If ur lazy u can just run it [here](https://replit.com/@TTkindBoi/Spelling-bee-solver?v=1)
