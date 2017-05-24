# Call By Value & Reference

- 결론, 자바는 항상 Call By Value 이다.

- Call By Reference는 C언어 &로 구현이 가능하다.


    void main(){
        int a = 1, b = 1, x = 1;
        int* c = &x;
        
        modify(a, &b, c);
        printf("%d %d %d", a, b, x);
    }
    
    void modify(int p, int* q, int* r){
        p = 2;
        *q = 2;
        *r = 2;
    }
    
    // 출력 결과 : 1 2 2
    
    // a는 Call By Value
    // b는 Call By Reference
    // x는 Call By Value
    
- 포인터를 넘기는 경우에도, 포인터를 &를 통해 직접 넘길 경우 Call By Reference이다.
- 포인터를 복사 후 넘기게 된다면 Call By Value가 된다.


- 참고 자료
1. https://en.wikipedia.org/wiki/Evaluation_strategy#Call_by_reference
2. https://stackoverflow.com/questions/40480/is-java-pass-by-reference-or-pass-by-value/12429953#12429953
