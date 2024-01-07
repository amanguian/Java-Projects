 
public class Basket {
    private MarketProduct[] marketArr;
 
 
    //constructor
    public Basket(){
        this.marketArr = new MarketProduct[0];
 
    }
 
 
    //make the shallow copy
    public MarketProduct[] getProducts(){
 
        MarketProduct[] copy_array = new MarketProduct[this.marketArr.length];
 
        for (int i=0; i<this.marketArr.length; i++){
            copy_array[i] = this.marketArr[i];
        }
        return copy_array;
    }
 
 
 
    public void add(MarketProduct product){
 
        //let's create a temporary array
        MarketProduct[] temp = new MarketProduct[marketArr.length];
 
        for(int i=0; i<marketArr.length; i++){
            temp[i] = this.marketArr[i];
        }
 
        this.marketArr = new MarketProduct[marketArr.length +1];
 
 
        for (int i=0; i<this.marketArr.length-1; i++){
            this.marketArr[i] = temp[i];
 
        }
        //let's add the element at the last index
        this.marketArr[marketArr.length-1] = product;
 
    }
 
    public boolean remove(MarketProduct product2){
 
        MarketProduct[] tempArray= new MarketProduct[this.marketArr.length-1];
        for(int i=0; i<this.marketArr.length; i++){
            if (this.marketArr[i].equals(product2)){
 
                //let's use another index a
                for (int a = i; a<this.marketArr.length-i;a++){
                    tempArray[a] = this.marketArr[a+1];
                }
                this.marketArr = tempArray;
                return true;
            }
            if(i != (this.marketArr.length-1)){
                tempArray[i] = this.marketArr[i];
            }
 
        }
        return false;
 
    }
 
 
    public void clear(){
 
        this.marketArr = new MarketProduct[0];
 
    }
 
    public int getNumOfProducts(){
        return this.marketArr.length;
    }
 
 
    public int getSubTotal(){
        //let's create a variable where the sum of the costs is gonna be stored
        int costs = 0;
 
        for (int i=0; i<this.marketArr.length; i++){
            costs += this.marketArr[i].getCost();
        }
        return (int) costs;
 
    }
 
    public int getTotalTax(){
        int temp = 0;
        for (int i=0; i<this.marketArr.length; i++){
            if (this.marketArr[i] instanceof Jam){
                temp += this.marketArr[i].getCost()*0.15 ;
            }
        }
        int total_tax = temp;
 
        return (int) total_tax;
    }
 
    public int getTotalCost(){
        return (this.getSubTotal() + this.getTotalTax());
    }
 
 
 
 
    public String converter(int i) {
 
        if (i <= 0) {
            return ("-");
 
        }
 
 
        String s = "" + i;
        int length_nbr = s.length();
 
        int dollars = (int) i/100;
        int rest = (int) i - (dollars * 100);
 
        String a = "" + dollars;
        String b = "" + rest;
 
 
        if (b.length()==1) {
            b = "0"+ b;
        } else {
            b = "" + rest;
        }
        return a + "." + b;
    }
 
 
 
 
    public String toString(){
 
 
            String to_return = new String();
 
            for (int i = 0; i < this.marketArr.length; i++) {
                to_return += this.marketArr[i].getName() + "\t" + converter(this.marketArr[i].getCost()) + "\n";
            }
 
 
 
 
            return (to_return + "\n" + "Subtotal" + "\t" + converter(this.getSubTotal()) + "\n" + "Total Tax"
                    +"\t"+ converter(this.getTotalTax()) + "\n" +"\n" +"Total Cost" +"\t"+ converter(getTotalCost()));
 
 
        }
    }
