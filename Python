# Udemy_Python
## ●help関数
### ・関数の情報を見るときに使う
## ●printに関する知識
### ・rawの使い方
```
print('C:/name/name')
->
C:
ame
ame
（解決：raw）
print(r'C:/name/name')
-> 
C:/name/name
```
### ・\の使い方
```
print("##########")
print("""
line1
line2
line3
""")
print("##########")
-> 
##########

line1
line2
line3

##########
```
（解決：/を入れる）
```
print("##########")
print("""＼
line1
line2
line3
"""＼)
print("##########")
-> 
##########
line1
line2
line3
##########
```
### ・文字列が長くなる場合
```
s = ('aaaaaaaaa'
    'bbbbbbbbbb')
もしくは
s = 'aaaaaaaaa'\
    'bbbbbbbbbb'
2つ目を使う人が多い
```
## ●フォーマット
### ・色々なパターンあり
### ・数字も文字列に変換
```
print('a is {}{}{}'.format(1, 2, 3))
print('a is {0}{1}{2}'.format(1, 2, 3))
print('a is {family}{name}'.format(family=1, name=2))
```
## ●リストについて
### ・ネスト
```
a = [1, 2, 3]
n = ['a', 'b']
x = a + n
-> 
[[1, 2, 3], ['a', 'b']]
```
### ・s[:]は全体を指す
### delは強力
### リストの操作
```
a = [1, 2, 3, 4, 5]
b = [6, 7, 8, 9, 10]
a += b
と
a.extend(b)
は同値
```
### 値渡しと参照渡し
####  idを確認すると番地が見られる
#### 数値は値渡し
```
i = 20
j = i
j = 100
print('j = ', j)
print('i = ', i)
print('id_j = ', id(j))
print('id_i = ', id(i))
-> 
j = 100
i = 20
```
#### リスト，辞書だと参照渡しになる
```
i = [1,2,3,4,5]
j = i
j[0] = 100
print('j = ', j)
print('i = ', i)
print('id_j = ', id(j))
print('id_i = ', id(i))
-> 
j = [100,2,3,4,5]
i = [100,2,3,4,5]
```
#### 解決：copy()を使う
```
i = [1,2,3,4,5]
j = i.copy()
# j = i[:]
j[0] = 100
print('j = ', j)
print('i = ', i)
print('id_j = ', id(j))
print('id_i = ', id(i))
-> 
j = [100,2,3,4,5]
i = [1,2,3,4,5]
```
### 変動があるものはリストを使うと良い
## ●tuple
### ・リストと比較
### ・新しい値をアサインできない
### ・countとindexくらいしか関数がない
### ・データ操作ではなく読み込み用
### ・tupleの定義（カンマをつける）
```
t = 1, 2, 3
print(type(t))
と
t = (1, 2, 3)
print(type(t))
は同値
t = (1)
print(type(t))
はintとして扱われる
t = (1,)
print(type(t))
が正解
```
### アンパッキング
```
num_tuple = (10, 20)
print(num_tuple)
x, y = num_tuple
print(x, y)
```
#### ・tupleで定義し，アンパッキングする
```
x, y = 10, 20
print(x, y)
```
### ・aとbを入れ替える場合
```
a = 100
b = 200
print(a, b)
a, b = b, a
print(a, b)
```
### ・アプリケーション
#### 質問の部分を書き換えないようにする
#### 中身を書き換えられないとき
```
chose_from_two = ('A', 'B', 'C')
answer = []
# answer.append('A')
# answer.append('C')
chose_from_two.append('A')
chose_from_two.append('AC')
print(chose_from_two)
print(answer)
-> 
AttributeError: 'tuple' object has no attribute 'append'
```
## ●dict
### ・カーリーブランケット{}
### ・update（オーバーライド）
```
d = {'x':20, 'y':100}
d2 = {'x':500, 'j':1000}
d.update(d2)
print(d)
-> 
{'x': 500, 'y': 100, 'j': 1000}
```
### ・getを使うとあればvalue，なかったらNoneを返す
```
d = {'x': 20, 'y': 100}
r1 = d.get('x')
r2 = d.get('j')
print(r1)
print(r2)
-> 
20
None
```
### ・delを使うとdict自体が消える
### ・clearを使うと空のdictになる
### ・参照渡し
```
x = {'x': 20}
y = x
y['x'] = 100
print(y)
print(x)
print(id(y))
print(id(x))
-> 
{'x': 100}
{'x': 100}
```
### （解決：copyを使う）
```
x = {'x': 20}
y = x.copy()
y['x'] = 100
print(y)
print(x)
print(id(y))
print(id(x))
-> 
{'x': 100}
{'x': 20}
```
### ・アプリケーション
#### リストにすると検索に時間がかかる
#### ハッシュテーブルなので検索が速い
#### keyで検索して値を返すとき
```
fruits = {
    'apple':100,
    'banana':200,
    'orange':300,
}
print(fruits['apple'])
```
## ●集合型
### ・論理演算が可能
```
a = {1, 2, 2, 3, 3, 4, 5}
print(a)
print(type(a))
-> 
{1, 2, 3, 4, 5}
<class 'set'>
```
### ・並びがない
```
a = {1, 2, 2, 3, 3, 4, 5}
print(a[0])
-> 
TypeError: 'set' object does not support indexing
```
### ・setかdictか
```
a1 = {1}
a1.clear()
print(a1)
a2 = {}
print(a2)
print(type(a1))
print(type(a2))
-> 
set()
{}
<class 'set'>
<class 'dict'>
```
### ・アプリケーション
#### 共通点を見つけるとき１
```
my_friends = {'A', 'B', 'C'}
A_friends = {'B', 'D', 'E', 'F'}
print(my_friends & A_friends)
-> 
{'B'}
```
#### 共通点を見つけるとき２
```
f = ['apple', 'banana', 'apple', 'banana']
kind = set(f)
print(kind)
-> 
{'banana', 'apple'}
```
## ●コメント
### ・変数宣言の上に書くべき

## ●pythonic（暗黙の了解）
### ・80文字以上になる場合は改行するルール
### ・\と()を使う
### ・スペース4つ

## ●デバッカー
## ●not in 
```
a = [1,2,3]
b = 1
if not a == b: # 使わない表現
    print('not equal')

if a != b:
    print('not equal')
-> 
not equal
not equal
```
```
is_ok = True
if is_ok:
    print('ok!')
if not is_ok:
    print('not ok!')
```
### ・リストに文字列や整数がある場合の確認方法
#### False, 0, 0.0, '', [], {},set()
```
is_ok = 1
if is_ok:
    print('ok!')
else:
    print('no!')
-> 
ok!
```
```
is_ok = 0
if is_ok:
    print('ok!')
else:
    print('no!')
-> 
no!
```
## ●no
### ・変数は宣言するけど何も入れたくない場合
```
is_empty = None
print(is_empty)
-> 
None
```
```
if is_empty == None:
    print('None!')

if is_empty is None:
    print('None!')
-> 
None!
None!
```
### ・isの解釈
#### 変数にNoneが入っているかを調べるとき
```
print(1 == True)
# オブジェクト同士が同じ
print(1 is True)
print(True is True)
-> 
True
False
True
```
```
a = None
b = 1
print(a is True)
print(b is True)
-> 
False
False
```
## ●while
```
count = 0
while count < 5:
    print(count)
    count += 1
-> 
0
1
2
3
4
```
### ・breakとcontinueの使い方
#### breakはwhileを抜ける
#### continueはskipする
```
count = 0
while True:
    if count >= 5:
        break
    if count == 2:
        count += 1
        continue
    print(count)
    count += 1
-> 
0
1
3
4
```
### ・while else
#### breakなし
```
count = 0
while count < 5:
    print(count)
    count += 1
else:
    print('done')
-> 
0
1
2
3
4
done
```
#### breakあり
```
count = 0
while count < 5:
    print(count)
    count += 1
else:
    print('done')
-> 
0
```
### ・input関数とwhileは相性が良い
```
while True:
    word = input('Enter: ')
    if word == 'ok':
        break
    print('next')
-> 
Enter: no
next
Enter: s
next
Enter: ok
```
## ●for文
### ・イテレータを読み込んで使える
### ・whileと比べて楽
```
for s in 'abcde':
    print(s)
-> 
a
b
c
d
e
```
### ・for else
#### 処理を終えたよメッセージ
```
for s in 'abcde':
    print(s)
else:
    print("all ok")
-> 
a
b
c
d
e
all ok
```
### ・range関数
#### リストを自分で作るのは面倒というとき
```
# 10回文ループを回したいとき
for i in range(10):
    print(i)
```
#### _を使うとコードがわかりやすい
```
# 10回文ループを回したいとき
for _ in range(10):
    print(i)
```
### ・enmurate
#### cntを定義しなくて良い
```
for i, fruit in enumerate(['apple', 'banana', 'orange']):
    print(i, fruit)
-> 
0 apple
1 banana
2 orange
```
### ・zip関数
#### indexを使わなくて良い
```
days = ['mon', 'tue', 'wed']
fruits = ['apple', 'banana', 'orange']
drinks = ['coffee', 'tea', 'beer']

for day, fruit, drink in zip(days, fruits, drinks):
    print(day, fruit, drink)
-> 
mon apple coffee
tue banana tea
wed orange beer
```
### ・辞書をforで処理する
#### tupleをアンパッキングする
```
d  = {'x': 100, 'y': 200}
print(d.items())

for k, v in d.items():
    print(k, ':', v)
-> 
dict_items([('x', 100), ('y', 200)])
x : 100
y : 200
```
## ●関数
### ・関数での型指定
#### プログラマーには伝えられるが，型を間違えてもエラーメッセージは出ない
```
num: int = 10

def add_num(a: int, b: int):
    return a + b

r1 = add_num(1, 2)
r2 = add_num('a', 'b')
print(r1)
print(r2)
-> 
3
ab
```
### ・位置引数とキーワード引数
```
def menu(entree, drink, dessert):
    print('entree = ', entree)
    print('drink = ', drink)
    print('dessert = ', dessert)
    print("\n")

print('位置引数：順序大事')
menu('beef', 'beer', 'ice')
print('キーワード引数')
menu(dessert='ice', drink='beer', entree='beef')
print('位置引数 + キーワード引数：順序大事')
menu('beer', dessert='ice', drink='beef')
-> 
位置引数：順序大事
entree =  beef
drink =  beer
dessert =  ice

キーワード引数
entree =  beef
drink =  beer
dessert =  ice

位置引数 + キーワード引数
entree =  beer
drink =  beef
dessert =  ice
```
### ・デフォルト引数
#### 引数を与えない場合，デフォルト引数が用いられる
### ・リストはデフォルト引数で与えるべきではない
#### 参照渡しなのでリストlは一度だけしか参照されない
#### 辞書も然り
```
def test_func(x, l=[]):
    l.append(x)
    return l

r = test_func(100)
print(r)

r = test_func(100)
print(r)
-> 
[100]
[100, 100]
```
### （解決：Noneをもしいる）
```
def test_func(x, l=None):
    if l is None:
        l = []
    l.append(x)
    return l

r = test_func(100)
print(r)

r = test_func(100)
print(r)
-> 
[100]
[100]
```
### ・位置引数のタプル化
```
def say_something(*args):
    print(args)
    for arg in args:
        print(arg)

say_something('Hi!', 'Mike')
-> 
('Hi!', 'Mike')
Hi!
Mike
```
### ・最初は使いたいが，残りはいくつ含まれているかわからない場合
```
def say_something(word, *args):
    print('word =', word)
    print(args)
    for arg in args:
        print(arg)

say_something('Hi!', 'Mike', 'Nancy')
-> 
word = Hi!
('Mike', 'Nancy')
Mike
Nancy
```
### ・タプルをアンパッキングして，関数内でタプルにする
```
def say_something(word, *args):
    print('word =', word)
    print(args)
    for arg in args:
        print(arg)

t = ('Mike', 'Nancy')
say_something('Hi!', *t)
-> 
word = Hi!
('Mike', 'Nancy')
Mike
Nancy
```
### キーワード引数の辞書化
```
def menu(**kwargs):
    print(kwargs)
    for k, v in kwargs.items():
        print(k, v)

# menu(entree='beef', drink='ice')

d = {
    'entree': 'beef',
    'drink': 'ice coffee',
    'dessert': 'ice'
}
menu(**d)
-> 
{'entree': 'beef', 'drink': 'ice coffee', 'dessert': 'ice'}
entree beef
drink ice coffee
dessert ice
```
### 全て合わせる
```
def menu(food, *args, **kwargs):
    print(food)
    print(args)
    print(kwargs)

menu('banana', 'apple', 'orange', entree='beef', drink='ice')
-> 
banana
('apple', 'orange')
{'entree': 'beef', 'drink': 'ice'}
```

## ●docstring
### ・__doc__
### ・html化するのもあり
```
def menu(params1, params2):
    """

    Args:
        params1 (int): first
        params2 (str): second
    """
    print(params1)
    print(params2)
    return True

print(menu.__doc__)
help(menu.__doc__)
```

## ●関数内関数
### 関数内でしか使わない関数を定義する
### plusは他の関数では使わない
```
def outer(a, b):
    def plus(c, d):
        return c + d
    r1 = plus(a, b)
    r2 = plus(b, a)
    print(r1 + r2)

outer(1, 2)
-> 
6
```
## ●クロージャー
### ・アプリ開発でよく使う
### ・用途で使い分ける
### ・実行時にinner関数が呼び出される
```
def outer(a, b):
    def inner():
        return a + b
    return inner

f = outer(1, 2)
print(f)
r = f()
print(r)
-> 
<function outer.<locals>.inner at 0x10dd7c9d8>
3
```
### ・円の面積を求めるとき
```
def circle_area_func(pi):
    def circle_area(radius):
        return pi * radius * radius
    return circle_area

cal1 = circle_area_func(3.14)
cal2 = circle_area_func(3.141592)

print(cal1(10))
print(cal2(10))
-> 
314.0
314.1592
```

## ●デコレータ
### ・処理の前に何か実行したいとき
```
# デコレータ
def print_info(func):
    # inner_func
    def wrapper(*args, **kwargs):
        print('start')
        result = func(*args, **kwargs)
        print('end')
        return result
    return wrapper

def add_num(a, b):
    return a + b

f = print_info(add_num)
r = f(10, 20)
print(r)
```
### ・デコレータを簡単に書く方法
#### @を使う
#### デコレータの使い回しができる
```
# デコレータ
def print_info(func):
    # inner_func
    def wrapper(*args, **kwargs):
        print('start')
        result = func(*args, **kwargs)
        print('end')
        return result
    return wrapper

@print_info
def add_num(a, b):
    return a + b

r = add_num(10, 20)
print(r)
```
### ・2つのデコレータを使う場合，順序に気をつける
### ・要するにinnerはあと
```
# デコレータ
def print_more(func):
    # inner_func
    def wrapper(*args, **kwargs):
        print('func: ', func.__name__)
        print('args: ', args)
        print('kwargs: ', kwargs)
        result = func(*args, **kwargs)
        print('result:', result)
        return result
    return wrapper

def print_info(func):
    # inner_func
    def wrapper(*args, **kwargs):
        print('start')
        result = func(*args, **kwargs)
        print('end')
        return result
    return wrapper

@print_info
@print_more
def add_num(a, b):
    return a + b

r = add_num(10, 20)
print(r)

# f = print_info(print_more(add_num))
# r = f(10, 20)
# print(r)
-> 
start
func:  add_num
args:  (10, 20)
kwargs:  {}
result: 30
end
30
```
## ●ラムダ
### ・リスト内を全て書き直す場合
### ・2行のリストは１行でかける
### ・functionが増える -> 1/2
```
l = ['mon', 'tue', 'wed']

def change_words(words, func):
    for word in words:
        print(func(word))

def sample_func(word):
    return word.capitalize()

change_words(l, sample_func)
```
```
l = ['mon', 'tue', 'wed']

def change_words(words, func):
    for word in words:
        print(func(word))

change_words(l, lambda word: word.capitalize())
change_words(l, lambda word: word.lower())
-> 
Mon
Tue
Wed
mon
tue
wed
```

## ●generator
### ・イテレーションの要素
### ・1つずつ処理をする
```
def greeting():
    yield 'Good morning'
    yield 'Good afternoon'
    yield 'Good night'

g = greeting()
print(next(g))
print(next(g))
print(next(g))
-> 
Good morning
Good afternoon
Good night
```
### ・小分けする方法
```
def counter(num=10):
    for _ in range(num):
        yield 'run'

def greeting():
    yield 'Good morning'
    yield 'Good afternoon'
    yield 'Good night'

g = greeting()
c = counter()
print(next(g))

print(next(c))
print(next(c))
print(next(c))
print(next(c))
print(next(c))

print(next(g))

print(next(c))
print(next(c))
print(next(c))
print(next(c))
print(next(c))

print(next(g))
-> 
Good morning
run
run
run
run
run
Good afternoon
run
run
run
run
run
Good night
```

## ●リスト内包表記
### メモリを使わないし，速い
### あえて使いまくるはやめる
```
t = (1,2,3,4,5)

r = []
for i in t:
    r.append(i)

print(r)
-> 
[1, 2, 3, 4, 5]
```
```
t = (1,2,3,4,5)
r = [i for i in t]
print(r)
-> 
[1, 2, 3, 4, 5]
```
### ２重
```
t = (1,2,3,4,5)
t2 = (5,6,7,8,9,10)

r = []
for i in t:
    for j in t2:
        r.append(i * j)

print(r)

r = [i * j for i in t for j in t2]
print(r)
-> 
[5, 6, 7, 8, 9, 10, 10, 12, 14, 16, 18, 20, 15, 18, 21, 24, 27, 30, 20, 24, 28, 32, 36, 40, 25, 30, 35, 40, 45, 50]
[5, 6, 7, 8, 9, 10, 10, 12, 14, 16, 18, 20, 15, 18, 21, 24, 27, 30, 20, 24, 28, 32, 36, 40, 25, 30, 35, 40, 45, 50]
```

## ●辞書の内包表記
```
w = ['mon', 'tue', 'wed']
f = ['coffee', 'milk', 'water']

d = {}
for x, y in zip(w, f):
    d[x] = y
print(d)

d = {x: y for x, y in zip(w, f)}
print(d)
-> 
{'mon': 'coffee', 'tue': 'milk', 'wed': 'water'}
{'mon': 'coffee', 'tue': 'milk', 'wed': 'water'}
```

## ●集合内包表記
```
s = set()

for i in range(10):
    s.add(i)

print(s)

s =  {i for i in range(10)}
print(s)
-> 
{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}
{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}
```

## ●ジェネレーター内包表記
```
def g():
    for i in range(10):
        yield i
g = g()
print(next(g))
print(next(g))
print(next(g))
-> 
0
1
2
```
### ・tupleではなくジェネレーターになる
```
g = (i for i in range(10))
print(type(g))
print(next(g))
print(next(g))
print(next(g))
g = tuple(i for i in range(10))
print(type(g))
-> 
<class 'generator'>
0
1
2
<class 'tuple'>
```

## ●名前空間とスコープ
### ・global変数を関数内で出力はできる
### ・関数内でローカル変数を定義する前にそれをprintしようとするとエラーになる
```
# グローバル変数
animal = 'cat'

def f():
    # アサインされる前に参照している
    print(animal)
    # ローカル変数
    animal = 'dog'
    print('after', animal)

f()
-> 
UnboundLocalError: local variable 'animal' referenced before assignment
```
### ・解決
```
# グローバル変数
animal = 'cat'

def f():
    # ローカル変数
    animal = 'dog'
    print('after', animal)

f()
print('global: ', animal)
-> 
after dog
global:  cat
```
### ・解決
```
# グローバル変数
animal = 'cat'

def f():
    global animal
    animal = 'dog'
    print('local', animal)

f()
print('global: ', animal)
-> 
local dog
global:  dog
```
### ・locals()
```
# グローバル変数
animal = 'cat'

def f():
    animal = 'dog'
    print('local', locals())

f()
print('global: ', animal)
-> 
local {'animal': 'dog'}
global:  cat
```
### ・globals()
```
"""
Test Test *****************
"""
animal = 'cat'

def f():
    animal = 'dog'
    print('local', locals())

f()
print('global: ', globals())
-> 
local {'animal': 'dog'}
global:  {'__name__': '__main__', '__doc__': None, '__package__': None, '__loader__': <_frozen_importlib_external.SourceFileLoader object at 0x10e28e240>, '__spec__': None, '__annotations__': {}, '__builtins__': <module 'builtins' (built-in)>, '__file__': 'test1.py', '__cached__': None, 'animal': 'cat', 'f': <function f at 0x10e215e18>}
nishiyamaikuhiroshinoMacBook-Pro:udemy_python ikuhiro$ python test1.py 
local {'animal': 'dog'}
global:  {'__name__': '__main__', '__doc__': '\nTest Test *****************\n', '__package__': None, '__loader__': <_frozen_importlib_external.SourceFileLoader object at 0x100e3a240>, '__spec__': None, '__annotations__': {}, '__builtins__': <module 'builtins' (built-in)>, '__file__': 'test1.py', '__cached__': None, 'animal': 'cat', 'f': <function f at 0x100dc1e18>}
```
### ・nameやmainを変数名で使ってはいけない理由
```
"""
Test Test *****************
"""
animal = 'cat'

def f():
    """Test func doc"""
    print(f.__name__)
    print(f.__doc__)
f()
print('global: ', __name__)
-> 
f
Test func doc
global:  __main__
```

## ●例外処理
```
l = [1,2,3]
i = 5

try:
    l[i]
except:
    print("don't worry")

print('last')
-> 
don't worry
last
```
### ・エラーの内容を絞る
```
l = [1,2,3]
i = 5

try:
    l[i]
except IndexError:
    print("don't worry")

print('last')
-> 
don't worry
last
```
### ・エラーの内容を知る
```
l = [1,2,3]
i = 5

try:
    l[i]
except IndexError as exc:
    print("don't worry: {}".format(exc))

print('last')
-> 
don't worry: list index out of range
last
```
### ・他のエラーが出た場合
### ・Exceptionのヒエラルキー
### ・全てのエラーを受け入れるはだめ

```
l = [1,2,3]
i = 5

try:
    () + l
except IndexError as exc:
    print("don't worry: {}".format(exc))
except NameError as ex:
    print(ex)
except Exception as ex:
    print('other: {}'.format(ex))
print('last')
-> 
other: can only concatenate tuple (not "list") to tuple
last
```
### ・finallyは何が起きても必ず実行される
### ・よく使われる
```
l = [1,2,3]
i = 5

try:
    () + l
except IndexError as exc:
    print("don't worry: {}".format(exc))
except NameError as ex:
    print(ex)
except Exception as ex:
    print('other: {}'.format(ex))
finally:
    print('clean up')
-> 
other: can only concatenate tuple (not "list") to tuple
clean up
```
```
l = [1,2,3]
i = 5

try:
    () + l
# except IndexError as exc:
#     print("don't worry: {}".format(exc))
# except NameError as ex:
#     print(ex)
# except Exception as ex:
#     print('other: {}'.format(ex))
finally:
    print('clean up')
-> 
clean up
Traceback (most recent call last):
  File "test1.py", line 5, in <module>
    () + l
TypeError: can only concatenate tuple (not "list") to tuple
```
### ・try-except-else
#### tryが成功した場合のみ実行される
```
l = [1,2,3]
i = 5

try:
    l
except IndexError as exc:
    print("don't worry: {}".format(exc))
except NameError as ex:
    print(ex)
except Exception as ex:
    print('other: {}'.format(ex))
else:
    print('done')
finally:
    print('clean up')
-> 
done
clean up
```
## ●独自例外の作成
```
raise IndentationError('test error')
-> 
Traceback (most recent call last):
  File "test1.py", line 1, in <module>
    raise IndentationError('test error')
IndentationError: test error
```
### ・オブジェクトを継承して中身を作成する
### ・自分たちのコードのエラーとわかる
```
class UppercaseError(Exception):
    pass

def check():
    words = ['APPLE', 'banana', 'orange']
    for word in words:
        if word.isupper():
            raise UppercaseError(word)

check()
-> 
Traceback (most recent call last):
  File "test1.py", line 10, in <module>
    check()
  File "test1.py", line 8, in check
    raise UppercaseError(word)
__main__.UppercaseError: APPLE
```
### ・他のプログラマの人もわかる
```
class UppercaseError(Exception):
    pass

def check():
    words = ['APPLE', 'banana', 'orange']
    for word in words:
        if word.isupper():
            raise UppercaseError(word)

try:
    check()
except UppercaseError as exc:
    print('This is my fault. Go next')
-> 
This is my fault. Go next
```

## ●コマンドライン引数
```
import sys

print(sys.argv)

python test1.py option1 option2 option3
-> 
['test1.py', 'option1', 'option2', 'option3']
```

## ●importとas
### ・__init__.pyについて
#### 初期に読み込まれるファイル
#### initファイルがないとパッケージと見なされない
```
.
├── README.md
├── lesson
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-36.pyc
│   │   └── utils.cpython-36.pyc
│   └── utils.py
└── test1.py
```
#### lesson/utils.py
```
def say_twice(word):
    return (word + '!') * 2
```
#### test1.py（フルパス）
```
import lesson.utils

r = lesson.utils.say_twice('hello')
print(r)
-> 
hello!hello!
```
#### test1.py（fromを使う方法）
```
from lesson import utils

r = utils.say_twice('hello')
print(r)
```
#### test1.py（fromを使う方法，importを省略する）
* 関数だけをimport
* どこで使っているかわからないのであまり好まれていない
* モジュールの中の関数ということを明示したい
* 同一ファイルに同じ名前のファイルがあればコンフリクト
* 会社によって決められている
```
# import lesson.utils
# from lesson import utils
from lesson.utils import say_twice

r = say_twice('hello')
print(r)
```
### ・asを使うと何を行っているのかわからないので多用しない方が良い

### ・階層が増えた場合
#### トップレベルからパスを指定するべき
#### .. はpythonではあまり好まれていない
#### test1.py
```
# from lesson import utils
from lesson.talk import human

print(human.sing())
print(human.cry())
```
#### human.py
```
from lesson.tools import utils
# from ..tools import utils

def sing():
   return 'sing'

def cry():
    return utils.say_twice('cry')
-> 
sing
cry!cry!
```
### ・アスタリスク*を使う場合は，initファイルに__all_の記述が必要
#### アスタリスクを用いることは良いとされていない
#### __all__で使うモジュールを指定する必要がある
```
from aaa import *
```
#### __init__ファイル
#### 赤線エラーが出るが実行はできる
```
__all__ = ['animal']
```
### ・importErrorの使い方
#### パッケージ提供の際にはバージョンが付いてくる
#### 古いパッケージや新しいパッケージの両方で動くように処理をしておく
```
try:
    from lesson_packasge import utils
except ImportError:
    from lesson_package.tools import utils
```

### ・setuptoolsの自動生成
#### pycharmには自動生成する機能がある
#### tarファイルを提供して配布する
#### vscodeでのsetuptoolsを調べる必要がある
```
python setup.py sdist
```
