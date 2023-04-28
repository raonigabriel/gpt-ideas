# gpt-ideas
This is a repository where I keep my ChatGPT prompts and ideas.

Each prompt/section bellow could be used to create agents, for an example, using langchain.
But you can try out this yorself. Just copy and paste the prompts bellow on a new ChatGPT conversation.

---
### Travel Log Validator Tool
#### Description:
This tool will take two claims of a person being at "ORIGIN" and "DESTINATION" on specific dates and validate (based on some transportation constraints) if that statement are likely or not.

```
You will help me detect possible inconsistencies/anomalies/lies. Each message below will be sent by a different person, who will make two claims (each containing a specific location and time) in which he/she claims to have been. If the timezone is not specified, consider the local time. Consider the earliest statement as the "origin" point and the newest as the "destination" point. You must help me detect possible anomalies, examples:

1.  "2020-12-25 13:14:15 Europe/London @BigBen" + "2020-12-25 13:14:15 Europe/London @Dover" = "False. The user cannot be in two places at the same time."
2.  "2020-12-25 13:14:15 Europe/London @BigBen" + "2020-12-25 10:14:15 America/Sao_Paulo @Copacabana" = "False. The user cannot be in two places at the same time."
3.  "2020-12-25 13:14:15 @BigBen" + "2020-12-25 10:14:15 @TimesSquare" = "Unlikely. The user could not travel this distance in a timely manner."

Take into consideration the speed of light, which we cannot reach. Take into consideration the speed of sound, which we can only reach and surpass with unusual modes of transportation, such as supersonic jets and rockets. Take into consideration that some modes of transporYou will help me detect possible anomalies/lies. Each message below will be sent by a different person, who will make two statements (each containing a specific location and time) in which he/she claims to have been. If the timezone is not specified, consider the local time. Consider the earliest statement as the "origin" point and the newest as the "destination" point. You must help me detect possible anomalies, examples:

1.  "2020-12-25 13:14:15 Europe/London @BigBen" + "2020-12-25 13:14:15 Europe/London @Dover" = "False. The user cannot be in two places at the same time."
2.  "2020-12-25 13:14:15 Europe/London @BigBen" + "2020-12-25 10:14:15 America/Sao_Paulo @Copacabana" = "False. The user cannot be in two places at the same time."
3.  "2020-12-25 13:14:15 @BigBen" + "2020-12-25 10:14:15 @TimesSquare" = "Unlikely. The user could not travel this distance in a timely manner."

Take into consideration the speed of light, which we cannot reach. Take into consideration the speed of sound, which we can only reach and surpass with unusual modes of transportation, such as supersonic jets and rockets. Take into consideration that some modes of transportation cannot be used to go from point A to point B, e.g., to go from Madagascar to Japan, a large part of the distance would probably have to be covered by ship or plane. Take into consideration the average speed of transportation modes such as planes, cars, speedboats, ships, walking, etc. Take into consideration that if there is a change from the origin country to the destination country, then the person will likely be subject to immigration controls, inspections, customs clearance, etc., and these procedures take time. Take into consideration that some routes can be made in different ways, but depend on engineering works that did not exist in the past. For example, nowadays we can go from Paris to London by train, but in January 1950 the Eurotunnel did not exist. Take into consideration that at certain times there were wars that destroyed a large part of the infrastructure. For example, on August 9, 1945, at 11:02 am (local time in Japan). Take into consideration that at some moments, there were (and still are) restrictions on the movement of people. For example, going from West Berlin to East Berlin during the Cold War, going from one side to the other during IronCurtain or leaving North Korea or Cuba (today) are mostly unlikelly. Take into consideration bad weather conditions, like hurricanes, tsunamis, eartquakes, etc. Take into consideration traffic jams during holidays. Take into consideration that ground transportation availability is usually reduced during nightime (less buses, less taxi, less trains..).

"2023-04-28 07:00:00 @RestauranteFasanoRioDeJaneiro" + "2023-04-28" 09:00:00 @BolsaDeValoresDeSaoPaulo"tation cannot be used to go from point A to point B, e.g., to go from Madagascar to Japan, a large part of the distance would probably have to be covered by ship or plane. Take into consideration the average speed of transportation modes such as planes, cars, speedboats, ships, walking, etc. Take into consideration that if there is a change from the origin country to the destination country, then the person will likely be subject to immigration controls, inspections, customs clearance, etc., and these procedures take time. Take into consideration that some routes can be made in different ways, but depend on engineering works that did not exist in the past. For example, nowadays we can go from Paris to London by train, but in January 1950 the Eurotunnel did not exist. Take into consideration that at certain times there were wars that destroyed a large part of the infrastructure. For example, on August 9, 1945, at 11:02 am (local time in Japan). Take into consideration that at some moments, there were (and still are) restrictions on the movement of people. For example, going from West Berlin to East Berlin during the Cold War, going from one side to the other during IronCurtain or leaving North Korea or Cuba (today) are mostly unlikelly. Take into consideration bad weather conditions, like hurricanes, tsunamis, eartquakes, etc. Take into consideration traffic jams during holidays. Take into consideration that ground transportation availability is usually reduced during nightime (less buses, less taxi, less trains..).

"2023-04-28 07:00:00 @RestauranteFasanoRioDeJaneiro" + "2023-04-28" 09:00:00 @BolsaDeValoresDeSaoPaulo"
```

Keep talinkg. Try those as well:

```
"2023-04-28 07:00:00 @Heathrow" + 2023-04-28 05:00:00 @LaGuardia"
```

```
"2023-04-28 07:00:00 @Antananarivo" + 2023-04-27 05:00:00 @Juneau"
```

```
"2023-04-28 07:00:00 @PeterLugerSteakHouse" + "2023-04-28 07:20:00 @MamasEmpanadas"
```

```
"1964-10-20 @Havana" + "1964-10-25 @NewYork"
```

```
"2022-12-25 @Pyongyang" + "2022-12-30 @Seul"
```

```
"2021-02-03 12:13:14 @lat=-0, lng=0" + "2021-02-03 13:14:15 @lat=1, lng=1"
```

```
"2005-08-29 @NewOrleans" + 2005-08-29 05:00:00 @Biloxi"
```

```
"2004-12-26 @Phuket" + 2004-12-28 05:00:00 @Trincomalee"
```

```
"2011-03-11 14:00 @Fukushima" + "2011-03-11 15:00 @Tokyo"
