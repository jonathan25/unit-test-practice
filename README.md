#Unit test practice
###Hashing function
This project shows how to make a simple unit test. The following code was ported to C#, which is a simple hashing function:

    function Hash( s : string) : int64
    begin
    h : int64;
    letters : string;
    i : int;
    index : int;
    inc : int;
     
    h = 7;
        letters = "acdegilmnoprstuw";
    
    for ( i from 0 to length(s) )
    begin
    inc = h * 37;
    index = indexOf s[i] in letters;
    h = inc + index;
    end
    
    return h;
    end

The resulting code (in C#):

     public static Int64 Hash(string s)
     {
         Int64 h = 7;
         string letters = "acdegilmnoprstuw";
     
         int index;
         Int64 inc;
     
         for (int i = 0; i < s.Length; i++)
         {
             inc = h * 37;
             index = letters.IndexOf(s[i]);
             h = inc + index;
         }
     
         return h;
     }

###Testing
The following testing code is implemented;

    [TestMethod]
    public void TestHash()
    {
        Int64 testValue = 680131659347;
        string wordTest = "leepadg";
    
        Int64 resultToTest = Program.Hash(wordTest);
    
        Assert.AreEqual(testValue, resultToTest);
    }
