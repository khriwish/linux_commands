cat data.txt | tr 'a-z' 'n-za-m' | tr 'A-Z' 'N-ZA-M'

'a-z' 'n-za-m' we use this since we know that everything is shifted 13 positions and if we want to shift 'a' then we start with 'b' until 'n' which is the 13th position, so we get the new abcde... as 'n-za-m' = 'n o p q r s t u v w x y z a b c d e f g h i j k l m'
