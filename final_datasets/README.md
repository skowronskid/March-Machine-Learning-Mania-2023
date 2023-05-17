##### Features explanation
For training dataset each row is a match that happened in a tournament. Columns with prefix 'T1_' are features of Team 1 - a team with a lower TeamID. Of course columns with prefix 'T2_' are features of the opposing team. For both men's and women's datasets and for  both teams in each match there are columns (naming T1_/T2_<column_name>):
1. TeamID - it's an ID remove this before training
2. Regarding their performance during regular season (only the season when the tournament took place, no past/future data)
    - features split by home/away game location. (Jeśli wyjdą mocno wspóliniowe, albo ogolnie bedzie decyzja zeby je usunac i nie wiadomo bedzie jak to moze po prostu wziac z nich srednia?, albo wyrzucic home i zostawic away away ktore moze lepiej prezentowac sytuacje na turnieju)
        - FG%_<home/away>_mean - average shot percentage from game (trafione rzuty/wszystkie rzuty) while playing  at home or away 
        - 3P%_<home/away>_mean - average 3 point shot percentage from game (trafione rzuty za 3 /wszystkie rzuty za 3) while playing at home oraway 
        - point_dff_<home/away>_mean - average score difference at the end of a match while playing at home or away
        - win_<home/away>_mean - win ratio while playing at home or away 
    - average features from the whole season 
        - Score_mean - average score by a team
        - FGM_mean - average made shots (made znaczy trafione jak coś)
        - FGM3_mean - average made 3 point shots
        - FGA_mean - average attempted shots (to sa ogolnie wszystkie rzuty oddane oprocz osobistych - to sa te "rzuty wolne" jakby)
        - FGM3_mean = average attempted 3 point shots
        - OR_mean - average offensive rebounds (zbiórki w ataku)
        - DR_mean - average defensive rebounds (zbiórki w obronie)
        - Ast_mean - average assists
        - TO_mean -average turnovers (straty)
        - Stl_mean - average steals (przechwyty)
        - Blk_mean -average blocks 
        - PF_mean - average personal fouls committed
    - average features from the whole season for the opponents (the opponent is not T2 for T1 here - those are the stats that the team's opponents averaged while playing against them). Same as above but with "opponent_" prefix after "T1_" or "T2_".
    - other features for a team for the season
        - win_mean - win ratio from all the games in the season
        - win_ratio_last_month - win ration from the games that took place up to 30 days before the start of the tourney
    - conference features - some conferences are better than others, those features look at matches played between different conferences in this season and averages the outcomes
        - conference_win_margin - average win ratio for this team's conference vs other conferences
        - conference_point_margin - average point difference for this team's conference while playing against other conferences
    - ranking score:
        - (FOR MEN ONLY) OrdinalRank - some rank at the end of the season
        - (FOR WOMEN ONLY) Ranking - some other rank at the end of the season 
3. Tourney data
    - previous tourney data
        - played_prev_tourney - whether the team played in the last year's tourney 
        - prev_win_ratio - if the team played in the last tourney what was their win ratio, if they haven't this value is 0
    - (FOR MEN ONLY) - previous appearances:
        - top1 - won the tourney
        - top2 - placed 2nd but didn't win
        - top4 - 3/4 place
        - top8 - 5-8 places
        - top16 - 9-16 places
        - top32 - 17-32 places
        - top64 - not sure how those two work
        - top68 - not sure how those two work
        - total - all appearances summed up 
    - Seed - what is their seed in the tourney (not the previous tourney)
4. Non T1_/T2_ prefix columns, those columns don't have a prefix:
    - seed difference T1_Seed - T2_Seed
    - ***win*** - 1 - T1 won,  0 - T2 won 
    



    





    