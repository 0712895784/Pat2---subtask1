Morse code is a communication system that represents letters, numbers, and punctuation marks using standardized sequences of short and long signals, commonly known as "dots" and "dashes". These signals can be transmitted through various mediums like light, sound, or electrical pulses. Originally developed for the telegraph, it enabled faster long-distance communication by converting text into coded patterns
Morse code was developed out of a need for faster, more reliable long-distance communication than what was available in the 1830s. Samuel Morse, along with others, created the telegraph and its associated code after experiencing a personal tragedy that highlighted the limitations of then-current communication methods. The need to transmit information efficiently over long distances, coupled with the potential of electricity for communication, led to the invention of Morse code
Morse code is a system for transmitting text information using a series of dots and dashes (or short and long signals). These signals represent letters, numbers, and punctuation marks, allowing for communication through various means like telegraphs, flashing lights, or sound. The key to understanding Morse code lies in recognizing the unique dot and dash patterns assigned to each character, along with the specific spacing between them
#include <iostream>
#include <unordered_map>
#include <string>
#include <cctype>  // For toupper

// Morse code map for A-Z and 0-9
std::unordered_map<char, std::string> morseCode = {
    {'A', ".-"},    {'B', "-..."},  {'C', "-.-."}, {'D', "-.."},   {'E', "."},
    {'F', "..-."},  {'G', "--."},   {'H', "...."}, {'I', ".."},    {'J', ".---"},
    {'K', "-.-"},   {'L', ".-.."},  {'M', "--"},   {'N', "-."},    {'O', "---"},
    {'P', ".--."},  {'Q', "--.-"},  {'R', ".-."},  {'S', "..."},   {'T', "-"},
    {'U', "..-"},   {'V', "...-"},  {'W', ".--"},  {'X', "-..-"},  {'Y', "-.--"},
    {'Z', "--.."},
    {'0', "-----"}, {'1', ".----"},{'2', "..---"},{'3', "...--"},{'4', "....-"},
    {'5', "....."}, {'6', "-...."},{'7', "--..."},{'8', "---.."},{'9', "----."}
};

int main() {
    std::string input;

    std::cout << "Enter a short message in English: ";
    std::getline(std::cin, input);

    std::cout << "\nMorse Code Translation:\n";

    for (char c : input) {
        if (c == ' ') {
            std::cout << "/ ";  // Slash to separate words
        }
        else {
            c = std::toupper(c);
            if (morseCode.find(c) != morseCode.end()) {
                std::cout << morseCode[c] << " ";
            }
            // Ignore any characters not in the map
        }
    }

    std::cout << std::endl;
    return 0;
}
