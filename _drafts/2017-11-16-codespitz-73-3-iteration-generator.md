---
layout: post
title:  "[CodeSpitz73-3] ES6+ 기초편 3회차 정리!"
author: Kyle
date:   2017-11-16 20:47:49 +0900
categories: development
tags: ECMAScript6+ javacript language basic
image: /assets/images/js_800x800-619x619.jpg
---
## Interface
1. 인터페이스란 사양에 맞는 값과 연결된 속성키의 셋트
2. 어떤 Object라도 인터페이스의 정의를 충족시킬 수 있다.
3. 하나의 Object는 여러개의 인터페이스를 충족시킬 수 있다.

### Test Interface 만들기

```javacript
// 1
const object = {
    test(str) {
        return true;
    }
}

const Test = class {
    test(str) {
        return true;
    }
}

const test = new Test();
```

인터페이스 구현이 어려운 건 머릿속에만 있기 때문이다.
덕타이핑에서 나타나는 문제들.


## Iterator Interface

```javacript
// 2
const iterator = {
    data: [1,2,3,4],
    next() {
      return {
          done: this.data.length === 0,
          value: this.data.pop()
      };  
    }
};

let iResult = iterator.next();
log(iResult.value + ' : ' + iResult.done);
iResult = iterator.next();
log(iResult.value + ' : ' + iResult.done);
iResult = iterator.next();
log(iResult.value + ' : ' + iResult.done);
iResult = iterator.next();
log(iResult.value + ' : ' + iResult.done);
iResult = iterator.next();
log(iResult.value + ' : ' + iResult.done);
```