# KMP
KMP Getnext[] Getnextval

 typedef struct{
 	int length;
 	char *ch;
 }Str;
 
 void KMP(Str str,Str substr,int next[])
 
 {
 	int i,j;
 	i=j=1;
 	
 	while(i<str.length&&j<substr.length)
 	{
 		if(j==0||str.ch[i]==substr.ch[j])
 		{
 			++i;
 			++j;
		 }
		 else
		 j=next[j];
	 }
 }
 
 void getnext(Str substr,int next[])
 
 {
 	int i=1;
 	int t=0;
 	
 	next[1]=0;
 	while(i<substr.length)
 	{
 		if(t==0||substr.ch[i]==substr.ch[t])
 		{
 			++i;
 			++t;
 			next[i]=t;
		 }
		 else
		 t=next[t];
	 }
 }
 
 void get_nextval(Str substr,int nextval[])
 
 {
 	int i=1;
 	int t=0;
 	nextval[1]=0;
 	
 	while(i<substr.length)
 	{
 		if(t==0||substr.ch[i]==substr.ch[t])
 		{
 			++i;
 			++t;
 			if(substr.ch[i]!=substr.ch[t])
 			{
 				nextval[i]=t;
			 }
			 else
			    nextval[i]=nextval[t];
		 }
		 else
		 t=nextval[t];
	 }
 }
