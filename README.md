Your start-up's BA has told marketing that your website has a large audience in Scandinavia and surrounding countries. Marketing thinks it would be great to welcome visitors to the site in their own language. Luckily you already use an API that detects the user's location, so this is an easy win. 

The Task

* Think of a way to store the languages as a database (eg an object). The languages are listed below so you can copy and paste!
* Write a 'welcome' function that takes a parameter 'language' (always a string), and returns a greeting - if you have it in your database. It should default to English if the language is not in the database, or in the event of an invalid input.

The data
'english'=>'Welcome',
'czech'=>'Vitejte',
'danish'=>'Velkomst',
'dutch'=>'Welkom',
'estonian'=>'Tere tulemast',
'finnish'=>'Tervetuloa',
'flemish'=>'Welgekomen',
'french'=>'Bienvenue',
'german'=>'Willkommen',
'irish'=>'Failte',
'italian'=>'Benvenuto',
'latvian'=>'Gaidits',
'lithuanian'=>'Laukiamas',
'polish'=>'Witamy',
'spanish'=>'Bienvenido',
'swedish'=>'Valkommen',
'welsh'=>'Croeso'

Possible invalid inputs include:
IP_ADDRESS_INVALID - not a valid ipv4 or ipv6 ip address
IP_ADDRESS_NOT_FOUND - ip address not in the database
IP_ADDRESS_REQUIRED - no ip address was supplied

https://medium.com/@calebharnell/extracting-hash-values-from-user-input-b2ea3acd6280

20200730
NEW:
def greet(language)

  language_list = { 'english': 'Welcome', 'czech': 'Vitejte', 'danish': 'Velkomst', 'dutch': 'Welkom',
                    'estonian': 'Tere tulemast', 'finnish': 'Tervetuloa', 'flemish': 'Welgekomen', 'french': 'Bienvenue',
                    'german': 'Willkommen', 'irish': 'Failte', 'italian': 'Benvenuto', 'latvian': 'Gaidits',
                    'lithuanian': 'Laukiamas', 'polish': 'Witamy', 'spanish': 'Bienvenido', 'swedish': 'Valkommen',
                    'welsh': 'Croeso' }
                    
  language_list.each do |key, value|
    if key.to_s == language
      puts "Your chosen language is #{key}, #{value}"
    else
      puts "Language not found, please try again"
    end
  end 
end

greet("irish")

OLD:
def greet(your_lang, language_list)
  language_list.each do |key, value|
    if key.to_s == your_lang
      puts "Your language is #{your_lang}, #{value}!"
    end
  end
end

language_list = { 'english': 'Welcome', 'czech': 'Vitejte', 'danish': 'Velkomst', 'dutch': 'Welkom',
                  'estonian': 'Tere tulemast', 'finnish': 'Tervetuloa', 'flemish': 'Welgekomen', 'french': 'Bienvenue',
                  'german': 'Willkommen', 'irish': 'Failte', 'italian': 'Benvenuto', 'latvian': 'Gaidits',
                  'lithuanian': 'Laukiamas', 'polish': 'Witamy', 'spanish': 'Bienvenido', 'swedish': 'Valkommen',
                  'welsh': 'Croeso' }

print 'Please choose your language: '
input_text = gets.chomp.to_s

your_lang = input_text

greet(your_lang, language_list)
