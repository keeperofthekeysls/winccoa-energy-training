Если граф ориентированный сумма длин всех списков смежности равна количеству ребер. Если неориентированный, то сумма длин всех списков равна 2х количеству ребер.
В модели scl каждое оборудование имеет терминал (один или два) и ссылку на терминал к которому подключен. То есть V{tRef[k], tRef[k+1]}


[Оптимизация алгоритма]Отключение (снятие напряжения) не является критичным для схемы.

[Алгоритм очереди]Добавить.
В Enq – проверка tail == Q.Length (переполнение). Нужно либо увеличить массив, либо выбросить исключение.
В Deq – проверка head == tail (очередь пуста), иначе попытка удалить из пустой очереди.
Сброс индексов – после Deq массив не освобождается, а head только растёт. Со временем head и tail упрутся в конец. Нужна кольцевая логика (head = (head+1)%length, аналогично для tail) либо после каждого удаления сдвигать элементы (неэффективно).
GetQ – выводит все элементы массива, включая уже удалённые (null). Лучше выводить только от head до tail-1.

class Program
{
    static void Main(string[] args)
    {
        List<string> vertices = new()
        {
            "A",
            "B",
            "C",
            "D",
            "E"
        };

        List<(string First, string Second)> edges = new()
        {
            ("A", "B"),
            ("A", "C"),
            ("B", "D"),
            ("C", "D"),
            ("D", "E")
        };

        string[] randomValues = new string[11]
        {
            "Kite",
            "River",
            "Stone",
            "Cloud",
            "Forest",
            "Light",
            "Signal",
            "Bridge",
            "Vector",
            "Orbit",
            "Переполнение"
        };

        FIFO f = new FIFO();
        //for (int i = 0; i < randomValues.Length; i++)
        //{
        //    f.Enq(randomValues[i]);
        //}
        //for (int i = 0; i < 10; i++)
        //{
        //    f.Deq();
        //}
        f.GetQ();
        bool r = true;
        int x = 0;
        
        while (r)
        {
            string w = Console.ReadLine();
            
            if (w == "1")
            {
                if (x == randomValues.Length) x = 0;
                f.Enq(randomValues[x]);
                ++x;
            }
            if (w == "2") f.Deq();
            if (w == "3") break;
        }
           
        Console.ReadLine();
    }

    public class FIFO()
    {
        bool bE = true;
        bool dE = false;
        int head, tail = 0;
        string[] Q = new string[3];

        public void Deq()
        {
            
            if (head == Q.Length) head = 0;
            else
            {
                if (head == tail)
                {
                    Console.WriteLine("Очередь равна/пуста");
                }
                else
                {
                    float d = head + 1 % Q.Length;
                    Console.WriteLine(d);
                    Console.WriteLine("Извлечение объекта");
                    Q[head] = null;
                    head++;
                }
                
            }

            //GetQ();
            
        }
        public void Enq(string inq)
        {
            bool boolEnq = false;
            
            if ((tail==Q.Length) && (Q[head] != null))
            {
                Console.WriteLine("достигнут конец очереди и данные не извлекались. Вставка следующего объекта невозможна.Объект [{0}] не будет помещен в очередь", inq);
                boolEnq = false;
                
            }
            if ((tail == Q.Length) && (Q[head] == null))
            {
                tail = 0;
                boolEnq = true;
            }
            if (head == tail + 1)
            {
                Console.WriteLine("Вставка невозможна");
                boolEnq = false;
            }
           
            if (bE && tail<Q.Length)
            {
                Console.WriteLine("Вставка объекта {0}", inq);
                Q[tail] = inq;
                tail++;
            }
            GetQ();
        }
        public void GetQ()
        {
            for (int i = 0; i < Q.Length; i++)
            {
                if (Q[i] == null) Console.Write(Q[i] + "{0}:NULL ",i);

            }
        }
        
    }
    public class BSF()
    {
        //Дерево поиска в ширину. 
        string[] tree = new string[] { };
        List<(string ver, string first, string second)> treeBSF = new();

        /// <summary>
        ///Список смежностей 
        /// </summary>
        List<(string ver, string[] vered)> adj = new();

        //Открыта вершина?
        bool isOpen = false;

        /// <summary>
        ///Хранит предшественника
        /// </summary>
        string parent = "";


        /// <summary>
        /// Статус вершины. 0-не открыта (белая), 1-открыта (серая), 2-открыта и нет больше серых или белых вершин (черная)
        /// </summary>
        int status = 0;
        
    }
}
