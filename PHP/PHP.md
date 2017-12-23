# PHP

## Arrays

array_reverse — Inverse l'ordre des éléments d'un tableau
array array_reverse ( array $array [, bool $preserve_keys = false ] )

array_flip — Remplace les clés par les valeurs, et les valeurs par les clés
array array_flip ( array $trans )

array_keys — Retourne toutes les clés ou un ensemble des clés d'un tableau
array array_keys ( array $input [, mixed $search_value = NULL [, bool $strict = false ]] )

array_keys() retourne les clés numériques et littérales du tableau input.
Si l'option search_value est spécifiée, seules les clés ayant cette valeur seront retournées. Sinon, toutes les clés de input sont retournées.

natsort — Trie un tableau avec l'algorithme à "ordre naturel"
bool natsort ( array &$array )
natsort() implémente un algorithme de tri qui traite les chaînes alphanumériques du tableau array comme un être humain tout en conservant la relation clé/valeur. C'est ce qui est appelé l'"ordre naturel". Un exemple de la différence de traitement entre un tel algorithme et un algorithme de tri de chaînes (comme lorsqu'on utilise sort()) est illustré ci-dessous.

natcasesort — Trie un tableau avec l'algorithme à "ordre naturel" insensible à la casse


## Links

https://github.com/ziadoz/awesome-php

https://github.com/jakoch/awesome-composer
