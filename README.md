# utl-finding-the-position-and-value-of-the-maximum-in-an-n-dimensional-array
Finding the position and value of the maximum in an n dimensional array  
    Finding the position and value of the maximum in an n dimensional array                                                          
                                                                                                                                     
    https://tinyurl.com/yyjqx4e8                                                                                                     
    https://stackoverflow.com/questions/17935199/how-to-identify-positions-of-max-value-in-an-array                                  
                                                                                                                                     
    Simon ohanlon                                                                                                                    
    https://stackoverflow.com/users/1478381/simon-ohanlon                                                                            
                                                                                                                                     
    SAS Forum                                                                                                                        
    https://tinyurl.com/y2bt5jmg                                                                                                     
    https://communities.sas.com/t5/SAS-Programming/Multi-Dimensional-Array-Checking-for-match-and-take-the-minimum/m-p/685355        
                                                                                                                                     
    Thought about SAS Peek but getting the position might be tricky?                                                                 
                                                                                                                                     
    /*                   _                                                                                                           
    (_)_ __  _ __  _   _| |_                                                                                                         
    | | `_ \| `_ \| | | | __|                                                                                                        
    | | | | | |_) | |_| | |_                                                                                                         
    |_|_| |_| .__/ \__,_|\__|                                                                                                        
            |_|                                                                                                                      
    */                                                                                                                               
                                                                                                                                     
    Three dimensional array                                                                                                          
                                                                                                                                     
    %let ary=%str(array(c(1:3,9,5:8), dim=c(2,2,2)));                                                                                
                                                                                                                                     
    /*          _                                                                                                                    
     _ __ _   _| | ___  ___                                                                                                          
    | `__| | | | |/ _ \/ __|                                                                                                         
    | |  | |_| | |  __/\__ \                                                                                                         
    |_|   \__,_|_|\___||___/                                                                                                         
                                                                                                                                     
    */                                                                                                                               
      [, , 1]                                                                                                                        
                                                                                                                                     
            [,1] [,2]                                                                                                                
       [1,]    1    3       see brackets                                                                                             
       [2,]    2    9 Max=9 Position =[2,] [,2] [,,1]                                                                                
                            Drop commas [2,2,1]                                                                                      
       , , 2                                                                                                                         
                                                                                                                                     
            [,1] [,2]                                                                                                                
       [1,]    5    7                                                                                                                
       [2,]    6    8                                                                                                                
                                                                                                                                     
    /*           _               _                                                                                                   
      ___  _   _| |_ _ __  _   _| |_                                                                                                 
     / _ \| | | | __| `_ \| | | | __|                                                                                                
    | (_) | |_| | |_| |_) | |_| | |_                                                                                                 
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                                
                    |_|                                                                                                              
    */                                                                                                                               
                                                                                                                                     
     "MAXIMUM VALUE"                                                                                                                 
      9                                                                                                                              
                                                                                                                                     
     "POSITION OF MAXIMUM VALUE"                                                                                                     
                                                                                                                                     
      dim1 dim2 dim3                                                                                                                 
                                                                                                                                     
         2    2    1                                                                                                                 
                                                                                                                                     
    /*         _       _   _                                                                                                         
     ___  ___ | |_   _| |_(_) ___  _ __                                                                                              
    / __|/ _ \| | | | | __| |/ _ \| `_ \                                                                                             
    \__ \ (_) | | |_| | |_| | (_) | | | |                                                                                            
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|                                                                                            
                                                                                                                                     
    */                                                                                                                               
                                                                                                                                     
    %utl_submit_r64(resolve('                                                                                                        
    x <- &ary;                                                                                                                       
    x;                                                                                                                               
    pos=which( x==max(x,na.rm=T) , arr.ind = T );                                                                                    
    "MAXIMUM VALUE";                                                                                                                 
    x[pos];                                                                                                                          
    "POSITION OF MAXIMUM VALUE";                                                                                                     
    pos;                                                                                                                             
    '));                                                                                                                             
                                                                                                                                     
                                                                                                                                     
