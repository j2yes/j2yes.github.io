---
title: how to use markdown
# comments: true
# other options
---

[TOC]

## markdown으로 글쓰기

### 목차만들기

```
[TOC]
```

### 제목을 지정해보자

```
# H1
## H2
### H3
#### H4
##### H5
###### H6
```

### 링크 첨부하기

```
[Link1](https://j2yes.github.io/)

[feedback@example.com](mailto:feedback@example.com)
```
> [Link1](https://j2yes.github.io/)

> [feedback@example.com](mailto:feedback@example.com)

### 이미지 첨부하기

```
![background](/assets/devops/jenkins/1.png "Optional title")
```

![background](/assets/devops/jenkins/1.png "Optional title")

### 파일(PDF) 첨부하기

```
[다운로드](/assets/mydoc.pdf)
```

> [다운로드](/assets/mydoc.pdf)

### 코드(GIST) 첨부하기

```
{% gist j2yes/3451d495ee5b9a601385 %}
```

{% gist j2yes/3451d495ee5b9a601385 %}

### 코드블럭 첨부하기

[하이라이터 지원 언어 목록](https://haisum.github.io/2014/11/07/jekyll-pygments-supported-highlighters/)

    스페이스 4칸 or Tab
    or
    ```shell
    ps -ef | grep oh
    ```
    or
    ```javascript
    console.log('oh');
    ```
    or
    ```java
    static void main(String args[]){
    }
    ```
    or
    ```ruby
    def support
    end
    ```

### 수평선으로 구분하기

```
---
or
***
or
___
```

### 번호 없는 리스트

```
+ Java
- Python
* Ruby
```

+ Java
- Python
* Ruby

### 번호 있는 리스트

```
1. 첫번째
2. 두번째
3. 세번째
```

1. 첫번째
2. 두번째
3. 세번째

### 체크박스 

```
- [ ] 리스트1
- [X] 리스트2
```

- [ ] 리스트1
- [X] 리스트1

### 텍스트에 효과주기

```
**두껍게**
~~취소선~~
```

기본글씨

**두껍게**

~~취소선~~

### \` 사용하기

```
\`
```

> \`

### 음영효과주기

```
`keyword`
```

`keyword`

### 태그만들기

@(Sample notebook)[Marxico|Manual|Markdown]

### LaTeX expression
$$	x = \dfrac{-b \pm \sqrt{b^2 - 4ac}}{2a} $$

### Table
| Item      |    Value | Qty  |
| :-------- | --------:| :--: |
| Computer  | 1600 USD |  5   |
| Phone     |   12 USD |  12  |
| Pipe      |    1 USD | 234  |

### Diagrams
#### Flow charts
```flow
st=>start: Start
e=>end
op=>operation: My Operation
cond=>condition: Yes or No?

st->op->cond
cond(yes)->e
cond(no)->op
```
#### Sequence diagrams 
```sequence
Alice->Bob: Hello Bob, how are you?
Note right of Bob: Bob thinks
Bob-->Alice: I am good thanks!
```

> **Note:** You can find more information:

> - about **Sequence diagrams** syntax [here][http://bramp.github.io/js-sequence-diagrams/],
> - about **Flow charts** syntax [here][http://adrai.github.io/flowchart.js/].

### 참고사이트
* https://sourceforge.net/p/collapse/wiki/markdown_syntax/
* http://commonmark.org/help/tutorial/index.html
* https://guides.github.com/features/mastering-markdown/
* http://marxi.co/
