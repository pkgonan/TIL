# Ellipsis 
- 메소드 등에서 동일한 객체의 파라미터를 간추려 중복을 줄이는 방법

## How to Use?
    class Test{
        public static void main(String[] args) {
            ellipsis(1, 2, 3 ,4);
        }
        
        static void ellipsis(int...num) {
            for(int i=0; i<num.length; i++)
                System.out.print(num[i] + " ");
        }
    }
    
    // 출력 : 1 2 3 4
