---
title: 「Go」并发
subtitle: '使通信代替共享变量'
author: Airren
catalog: true
header-img: ''
tags:
  - null
p: go_basic/go_concurrency
date: 2020-08-05 00:14:06
---



简单的线程池

```go
package main

import (
	"fmt"
	"sync"
	"sync/atomic"
	"time"
)

var count int64
var ch = make(chan int)
var wg = sync.WaitGroup{}

func main() {

	startAt := time.Now()

	// build a  pool with 5 goroutine, every goroutine deal the data form the chan
	for i := 0; i < 5; i++ {
		wg.Add(1)
		go func() {
			defer wg.Done()
			for val := range ch {
				count = atomic.AddInt64(&count, 1)
				fmt.Printf("%vvar: %v\n", count, val)
				<-time.After(100 * time.Millisecond)
			}
		}()
	}

	fmt.Println(">>> Start Work")

	// task producer
	for i := 0; i < 20; i++ {
		ch <- i
	}

	close(ch)
	wg.Wait()
	fmt.Println(">>> Finished")
	totalTime := time.Now().Sub(startAt)
	fmt.Printf("Total time is %v, total task: %v, avg time: %v", totalTime, count, totalTime/20)
}

```

