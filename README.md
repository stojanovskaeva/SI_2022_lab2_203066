EVA STOJANOVSKA 203066

Control Flow Graph

![graph](https://user-images.githubusercontent.com/100574301/171850058-d86af5a2-f0f3-4b31-bb1d-91918dc729df.png)



    public static List<String> function(List<String> list) {
        if (list.size() <= 0) {                                                                                                                //1
            throw new IllegalArgumentException("List length should be greater than 0");                                                        //2
        }   
        int n = list.size();                                                                                                                   //3
        int rootOfN = (int) Math.sqrt(n);                                                                                                      //4
        if (rootOfN * rootOfN  != n) {                                                                                                         //5
            throw new IllegalArgumentException("List length should be a perfect square");          }                                           //6
        List<String> numMines = new ArrayList<>();                                                                                             //7                   
        for (int i = 0; i < n; i++) {                                                                                                          //8
            if (!list.get(i).equals("#")) {                                                                                                    //9
                int num = 0;                                                                                                                   //10
                if ( (i % rootOfN != 0 && list.get(i - 1).equals("#")) || (i % rootOfN != rootOfN - 1 && list.get(i + 1).equals("#")) ) {      //11
                    if ( (i % rootOfN != 0 && list.get(i - 1).equals("#")) && (i % rootOfN != rootOfN - 1 && list.get(i + 1).equals("#")) ){   //12
                        num += 2;                                                                                                              //13
                    }
                    else {                                                                                                                     //14
                        num  += 1;                                                                                                             //15
                    }
                }
                if (i - rootOfN >= 0 && list.get(i - rootOfN).equals("#")){                                                                    //16
                    num++;                                                                                                                     //17
                }
                if (i + rootOfN < n && list.get(i + rootOfN).equals("#")){							                   //18
                    num++;                                                                                                                     //19
                }
                numMines.add(String.valueOf(num));                                                                                             //20
            }
            else {                                                                                                                             //21
                numMines.add(list.get(i));                                                                                                     //22
            }
        }
        return numMines;                                                                                                                       //23
    }
}

Цикломатска комплексност

Цикломатска комплексност на извршениот код е 9 и го добив преку формулата CYC = E – N + 2. Во мојот случај CYC = 31 - 24 + 2 = 9. Буквата Е го означува бројот на рабовите а буквата N бројот на јазли во графот. 


