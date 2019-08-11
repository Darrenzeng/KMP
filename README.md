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
