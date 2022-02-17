# CSC-370
public class DrawTree {

    public static String[] draw(int[] parents, String[] names){
        if(parents[0] != -1) {
            return reversed(parents, names);
        }else{
            return forward(parents, names);
        }
    }

    private static String[] forward(int[] parents, String[] names) {
        String[] str = new String[parents.length];
        int tab=0;
        int prev=-1, current, next=0;
        for(int i=0;i<parents.length;i++) {
            String st = "";
            current = parents[i];
            if(i != parents.length-1)
                next = parents[i+1];
            for(int j=0;j<tab;j++){
                st += "\t";
                if(prev < current && j!=tab-1)
                    st += "|";
            }
            st += "+-"+names[i];
            str[i] = st;
            if(next != current){
                prev = current;
            }if(next > current){
                tab++;
            }else if(next < current)
                tab--;

        }
        return str;
    }

    private static String[] reversed(int[] parents, String[] names) {
        String[] str = new String[parents.length];
        int tab=0;
        int prev=-1, current, next=0;
        for(int i=parents.length-1;i>=0;i--) {
            String st = "";
            current = parents[i];
            if(i != 0)
                next = parents[i-1];
            for(int j=tab;j>0;j--){
                st += "\t";
                if(prev < current && j!=tab-1)
                    st += "|";
            }
            str[i] = st+"+-"+names[i];
            if(next != current){
                prev = current;
            }if(next < current){
                tab++;
            }else if(next > current)
                tab--;
        }
        return str;
    }

    public static void main(String[] args) {
        int[] parents = {-1,0,1,1,0,0,5,5};
        String[] names = {"Root","SubB","LEAF1","LEAF2","LEAF3","SubA","LEAF4","LEAF5"};
        String[] str=draw(parents, names);
        for(String s:str){
            System.out.println(s);
        }
    }
}
