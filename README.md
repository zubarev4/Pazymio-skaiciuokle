# Programos veikimas: 
1. Paleidus programą, vartotojo prašoma įvesti 1 - Generuoti failus.
2. Vartotojui sugeneruojami 5 failai su skirtingais studentų skaičiais: 1 000, 10 000, 100 000, 1 000 000, 10 000 000. Taip pat pateikiamas laikas, per kurį studentų failai buvo sukurti, nuskaityti, surūšiuoti ir išvesti į du naujus failus: viename paskirstyti visi studentai, kurių galutinis pažymis didesnis arba lygus 5 - kietekai, kitame studentai, kurių pažymis mažesnis nei 5 - vargšiukai.
3. Toliau vartotojo yra paklausiama, ar jis nori įvesti duomenis ar nuskaityti iš failo.
4. Jei pasirenkama, kad nuskaityti iš failo tai paklausiama iš kurio iš 4-ių failų norima nuskaityti.
5. Apskaičiavus rezultatus vartotojo paklausiama kaip jis norėtų rūšiuoti duomenis: vardas, pavardė, galutinis pagal vidurkį arba galutinis pagal medianą. 
6. Jei pasirenkama, kad įvesti duomenis tai paklausiama ar nori įvesti studento vardą bei pavardę ranka ar generuoti.
7. Paklausiama kokiu būdu norima įvesti pažymius (įrašyti ranka arba generuoti atsitiktinai).
8. Įrašius visus pažymius ir egzamino įvertinimą, vartotojui leidžiama pasirinkti pridėti dar studentų arba baigti žmonių įvedimą.
9. Pasirinkus vartotojui yra atspausdinamas sąrašas su visais studentais ir jų galutiniais vidurkiais ir medianomis.

*Pridėtos dvi kodo variacijos (Vienoje yra naudojamas deque, kitoje list)* 
*Pridėtos dvi studentų skirstymo strategijos 1 ir 2:*
### Naudojami sistemos parametrai
- CPU 11th Gen Intel(R) Core(TM) i7-1165G7 @ 2.80GHz Cores:	4 Logical processors:	8
- RAM 16GB
- HDD TOSHIBA MQ04ABF100 Capacity:	932 GB
- SDD PC SN530 NVMe WDC 512GB Capacity:	477 GB

## 1 Strategija
Bendro studentai konteinerio (vector, list ir deque tipų) skaidymas (rūšiavimas) į du naujus to paties tipo konteinerius: "vargšiukų" ir "kietiakų".
                                                  1000 Studentų

|                       | Vector                     | List                          | Deque                         |
|-----------------------|----------------------------|-------------------------------|-------------------------------|
| Skaitymas iš failo =  | 0.0083s                    | 0.0113s                       | 0.005s                        |
| Studentų rūšiavimas = | 0.0004s                    | 0.0037s                            | 0.00079s                       |
| Studentų skirstymas = | 0.0029s                    | 0.0066s                       | 0.0052s                       |

                                                 10000 Studentų

|                       | Vector                        | List                          | Deque                         |
|-----------------------|-------------------------------|-------------------------------|-------------------------------|
| Skaitymas iš failo =  | 0.0525s                       | 0.0849s                       | 0.049s                        |
| Studentų rūšiavimas = | 0.0033s                       | 0.0196s                        | 0.0071s                       |
| Studentų skirstymas = | 0.0202s                       | 0.0501s                       | 0.0334s                       |

                                                 100000 Studentų

|                       | Vector                        | List                          | Deque                         |
|-----------------------|-------------------------------|-------------------------------|-------------------------------|
| Skaitymas iš failo =  | 0.392s                        | 0.822s                        | 0.526s                        |
| Studentų rūšiavimas = | 0.0313s                       | 0.1933s                       | 0.0777s                       |
| Studentų skirstymas = | 0.1075s                       | 0.3514s                       | 0.310s                        |

                                                 1000000 Studentų

|                       | Vector                        | List                          | Deque                         |
|-----------------------|-------------------------------|-------------------------------|-------------------------------|
| Skaitymas iš failo =  | 3.72s                         | 8.2799s                       | 4.8748s                       |
| Studentų rūšiavimas = | 0.3307s                       | 1.8064s                       | 0.8815s                       |
| Studentų skirstymas = | 0.8901s                       | 2.5030s                       | 2.7656s                       |

                                                 10000000 Studentų

|                       | Vector                        | List                          | Deque                         |
|-----------------------|-------------------------------|-------------------------------|-------------------------------|
| Skaitymas iš failo =  | 39.046s                       | 75.0823s                      | 51.128s                      |
| Studentų rūšiavimas = | 3.6826s                       | 43.9935s                      | 41.4782s                       |
| Studentų skirstymas = | 9.9272s                       | 23.0101s                       | 21.2097s                      |

## 2 Strategijos tyrimai
Bendro studentų konteinerio (vector, list ir deque) skaidymas (rūšiavimas) panaudojant tik vieną naują konteinerį: "vargšiukai". 

                                                 1000 Studentų

|                       | Vector                     | List                          | Deque                         |
|-----------------------|----------------------------|-------------------------------|-------------------------------|
| Skaitymas iš failo =  | 0.0123s                    | 0.0213s                       | 0.005s                        |
| Studentų rūšiavimas = | 0.0004s                    | 0.0037s                            | 0.00079s                       |
| Studentų skirstymas = | 0.0029s                    | 0.0066s                       | 0.0052s                       |

                                                 10000 Studentų

|                       | Vector                        | List                          | Deque                         |
|-----------------------|-------------------------------|-------------------------------|-------------------------------|
| Skaitymas iš failo =  | 0.0625s                       | 0.0949s                       | 0.089s                        |
| Studentų rūšiavimas = | 0.0033s                       | 0.0196s                        | 0.0071s                       |
| Studentų skirstymas = | 0.0202s                       | 0.0501s                       | 0.0334s                       |

                                                 100000 Studentų

|                       | Vector                        | List                          | Deque                         |
|-----------------------|-------------------------------|-------------------------------|-------------------------------|
| Skaitymas iš failo =  | 0.792s                        | 0.922s                        | 0.726s                        |
| Studentų rūšiavimas = | 0.0313s                       | 0.1933s                       | 0.0777s                       |
| Studentų skirstymas = | 0.1075s                       | 0.3514s                       | 0.310s                        |

                                                 1000000 Studentų

|                       | Vector                        | List                          | Deque                         |
|-----------------------|-------------------------------|-------------------------------|-------------------------------|
| Skaitymas iš failo =  | 4.72s                         | 10.2799s                       | 6.8748s                       |
| Studentų rūšiavimas = | 0.3307s                       | 1.8064s                       | 0.8815s                       |
| Studentų skirstymas = | 0.8901s                       | 2.5030s                       | 2.7656s                       |

                                                 10000000 Studentų

|                       | Vector                        | List                          | Deque                         |
|-----------------------|-------------------------------|-------------------------------|-------------------------------|
| Skaitymas iš failo =  | 41.046s                       | 78.0823s                      | 55.128s                      |
| Studentų rūšiavimas = | 3.6826s                       | 43.9935s                      | 41.4782s                       |
| Studentų skirstymas = | 9.9272s                       | 23.0101s                       | 21.2097s                      |



### Instaliavimo instrukcija
- Jeigu naudojate „Visual Studio Code“, rekomenduojama įdiegti šiuos išplėtinius:
"C/C++ Extension Pack", "C/C++ Runner", "Code Runner", "CMake", "CMake Tools".
- Meniu juostos pasirinkite „Terminalas“ -> „Naujas terminalas“. Naujas terminalo langas turėtų atsirasti apačioje jūsų programos sąsajos.
Naudodami cd komandą, pateikite klonuoto saugyklos kelią: cd <jūsų\direktorijos\kelias>
Pavyzdžiui, cd<C:\Users\...>
- Norėdami paleisti programą, turite ją sukompiliuoti naudodami „Makefile“ failą, kuris yra saugykloje. Programos (pvz., VSCode) terminale rašykite:
make vektoriai
make failu-generavimas
make programa
