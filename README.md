Stronka - https://www.kaggle.com/competitions/march-machine-learning-mania-2023/


Rozwiązania ludzi:

* 1 miejsce pogadanka - https://www.kaggle.com/competitions/march-machine-learning-mania-2023/discussion/399553
* 1 miejsce solution - https://www.kaggle.com/code/rustyb/paris-madness-2023#Data-preparation! - Python
  (to chyba jest skonfigurowane rozwiązanie stąd https://www.kaggle.com/code/raddar/paris-madness)
* 2 miejsce pogadanka - https://www.kaggle.com/competitions/march-machine-learning-mania-2023/discussion/401578 (tam jest podane 5 notebooków z rozwiązaniami) - więcej zrobione, w R.


  



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

