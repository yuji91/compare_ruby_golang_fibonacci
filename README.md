# compare_ruby_golang_fibonacci

[Qiita: RubyからGoの関数をつかう](https://qiita.com/achm/items/679b3f3af2cf377f0f02) を参考。


## Rubyでの実行結果
```
$ time ruby fib.rb
102334155

real	0m19.115s
user	0m15.480s
sys	0m0.180s

2回目: 15.7s
3回目: 14.8s
```

## Golangでの実行結果
```
$ time go run fib.go
102334155

real	0m1.623s
user	0m1.048s
sys	0m0.365s

2回目: 1.8s
3回目: 1.7s
```

## 結果
Rubyで15秒かかる処理が2秒未満で完了した。

## Golang(build済)の実行結果
```
$ go build fib.go
time ./fib

102334155

real	0m0.776s
user	0m0.761s
sys	0m0.008s

2回目: 0.7s
3回目: 0.7s
```

## 結果
build済のファイルを実行すると1秒未満で完了した。

## RubyからGolangを呼び出した場合の実行結果

```
# 事前準備
$ go build -buildmode=c-shared -o fib_shared_library.so fib_shared_library.go 

$ time ruby fib_attach_golang.rb

102334155

real	0m1.393s
user	0m1.001s
sys	0m0.161s

2回目: 1.2s
3回目: 1.0s
```

## 結果
RubyからGolangでビルド済の関数を呼び出す形で実行すれば、15秒かかった処理が約1秒で完了した。
