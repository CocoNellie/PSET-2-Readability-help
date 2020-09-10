# PSET-2-Readability-help
I'm having issues with part of my code it will compile but not read anything after grade 1 please help. 
#include <stdio.h>
#include <cs50.h>
#include <ctype.h>
#include <string.h>
#include <math.h>

int main(void)
{
    string s = get_string("Text: ");
    int num_words, num_sentences, num_letters;
    num_words = num_sentences = num_letters = 0;

    for (int i = 0, len = strlen(s); i < len; i++)
    {
        if (isalpha(s[i]))
        {

            num_letters++;
        }

        else  if ((i == 0 && s[i] != ' ')

            || (i != len - 1 && s[i] == ' ' && s[i + 1]  != ' '))
        {
            num_words++;
        }
       else  if (s[i] == '.' || s[i] == '?' || s[i] == '!')
        {

            num_sentences++;

      }

      float L = (num_letters / (float) num_words) * 100;

      float S = (num_sentences / (float) num_words) * 100;

      int index = round(0.0588 * L - 0.296 * S - 15.8);

      if (index < 1)
     {

            printf("Before Grade 1\n");
            return 0;

        }
     else if (index >= 16)
     {
            printf("Grade 16+\n");
            return 0;
        }

    else

    {

            printf("Grade %i\n", index);
            return 0;

        }
    }
}
