___
# Co się dzieje? Co chcemy osiągnąć?

Generalnie mamy zmodelować na podstawie wyników z poprzednich turniejów, aktualnego sezonu 22/23, seedów do turniejów prawdopodobieństwo rezultatów meczy każdy vs każdy jakie mogą się wydarzyć turnieju w 2023. Wiemy jakie drużyny będą brały udział w turnieju bo mamy seedy na 2023 rok. Ramka, którą mamy otrzymać wygląda tak:

ID | Pred
---|---
2023_1101_1102 | 0.6
2023_1101_1103 | 0.4
2023_1101_1104 | 0.5
... | ...

Gdzie ID to indywidualne ID meczu zrobione jako 2023_(TeamID drużyny o mniejszym ID)_(TeamID drużyny o większym ID). Pred to prawdopodobieństwo tego, że drużyna o mniejszym ID wygra z drużyną o większym ID. Czyli na przykład dla pierwszego wiersza pstwo 0.6 oznacza, prawdopodobieństwo że drużyna 1101 wygra z drużyną 1102 w turnieju w 2023 roku.

W jednej ramce mamy zawrzeć wyniki turnieju mężczyzn i kobiet. Ich TeamID nie są takie same więc nie ma problemu z powtarzającym się ID. Oczywiście mężczyźni nie grają z kobietami.
