
파일입출력 경량화

```cs
StreamWriter writer = new StreamWriter(Console.OpenStandardOutput());

StreamReader reader = new StreamReader(Console.OpenStandardInput());

// 다쓰고 닫아줘야함
writer.Close();

reader.Close();

```
    

레인지만큼 리스트 만들기

```cs
List<int> numList = new List<int>(Enumerable.Range(1, 10000));
```


리스트 스트링으로 합쳐서 출력

```cs
Console.WriteLine(string.Join("\n",numList));
```
  

정렬 과 추가 정렬

```cs
var sortList = list.OrderBy(x => x.Item1).ThenBy(x => x.Item2).ToList();
```
  
  

문자열 스플릿하고 모두 형변환 하고싶을때

```cs
var buf = Array.ConvertAll(reader.ReadLine().Split(' '), int.Parse);
```


where 를 이용하여 리스트에서 값 탐색

```cs
int plus = arr.Where(x=> x>0).Count();
int minus = arr.Where(x => x<0).Count();
int zero = arr.Where(x=> x==0).Count();
```


숫자만 추출

```csharp
Regex.Replace(str, @"[^0-9]", "");
```


리스트와 배열

```cs
//길이 20인 배열 초기화
int[] IntArray = new int[20];

//길이 20인 리스트 초기화

List<int> IntList = new List<int>(new int[20]);
- 정석적인 방법은 for문을 돌려서 Add를 20번하는 것이다.  
- 20짜리 길이의 배열을 하나 더 만드는 거라서 명시적이지만 메모리를 낭비한다.  
- 같은 값을 넣기 위해서는 어차피 for문을 이용해야 하니 초기값으로 만들경우에만 사용할 것.  
- LINQ의 array.ToList();를 사용할 수도 있다
```
참고: https://mentum.tistory.com/278


중복값 제거

```cs
int[] numArray = { 1, 2, 2, 3, 3, 3, 4, 5, 5 }; 

int[] distArray = numArray.Distinct().ToArray();
```

그룹지어서 배열에서 한번만나오는 중복이없는 값찾기

```cs
       List<int> result = a.GroupBy(x => x)
                      .Where(g => g.Count() == 1)
                      .Select(x => x.Key)
                      .ToList();
```

중복요소 찾는링크

https://www.techiedelight.com/ko/find-duplicate-elements-in-a-list-in-csharp/


