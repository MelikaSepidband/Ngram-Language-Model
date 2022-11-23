# Ngram-Language-Model
The data is extracted from a persian news web site and the title of news is saved in "news_text.txt".  

class DataProcessor :  

clean_text : deleting characters that are not main characters, replace numbers with "N" ,
add \\s to beginning of sentences and \\e to end of them.  

get_most_freq : 200 most frequent tokens are saved in "frequent.txt" and returns frequencies_dict which is 10000 most frequent 
tokens, n_tokens, which is number of tokens and n_unique_tokens, which is number of unique tokens.  

handle_unknown : this function replace tokens that are not in frequencies_dict with "unk" .  
  

      
class NgramLanguageModel :  

make_ngram_dicts : this function returns unigram_dict, which is a dictionary of tokens and their frequencies,
bigram_dict, which is a dictionary of two-token phrases and their frequencies and trigram_dict, 
which is a dictionary of three-token phrases and their frequencies.  

calculate_smoothed_probs : this function gets n= 2 or 3 and a string. If n=2, it returns 
5 most probable tokens that can come after last 2 tokens of the string and their probablities. If n=3, it returns 
5 most probable tokens that can come after last 3 tokens of the string and their probablities.  

generate_text : this function gets a string and n= 2 or 3 and according to "calculate_smoothed_probs" 
generates new tokens and concat to the string until it sees the last character which is "\\e". 
If it stucks in a loop after 10 tokens, stops and return the sentence.  

evaluate_model : this function gets tokens of some sentences and according to the 5 first tokens of each sentence 
generate text with "genearte_text" function (for n=2 and n=3) and calculates "average log likelihood" 
for bigram and trigram for each sentence.  

pp_evaluate_model : this function is like "evaluate_model" function except it calculates "perplexity" 
for evaluation.  

We used 300 first sentences of the test data for evaluation.
