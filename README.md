<div align="center">

## The Story Of Resurrection


</div>

### Description

Explains the concepts of Garbage Collection and object resurrection in java. I have taken a novel approach so do comment/vote, please.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Abdul Rafay Mansoor](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/abdul-rafay-mansoor.md)
**Level**          |Beginner
**User Rating**    |5.0 (35 globes from 7 users)
**Compatibility**  |Java \(JDK 1\.1\), Java \(JDK 1\.2\)
**Category**       |[Classes](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/classes__2-83.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/abdul-rafay-mansoor-the-story-of-resurrection__2-4016/archive/master.zip)





### Source Code

<HR><br><B><FONT COLOR=red>
<KBD><H2>The Story Of Resurrection.</H2></KBD></FONT></B><br><br>
Once there lived an object of Criminal <FONT COLOR="#3300FF">class</font>, reffered as Rambo. he had many alias BigCat, BlackTiger, TheRock ...but they were all the same person.<br><br>
He committed a serious crime for which he was to be removed from this world (the heap), all his Refrences and Alises where <FONT COLOR="#3300FF">null</font>ed from records (stack) so that ShootingSquard (System.gc()) could take him. Rambo knew that any <FONT COLOR="#3300FF">Exception</font> he may <FONT COLOR="#3300FF">throw</font> at the Squard will not save him since his hour has come. what did your ancestors do in their final hours ?? asked the squad, I dont know I have to recall it explicitly answered rambo.<br><br>
As the traditions of the land (JVM), he was asked for any <FONT COLOR="#3300FF">final</font> wish before is death, the Squard promised to fulfill if in mood (?) , the cunning Rambo immediately asked for resurrection, bound by the promise the moody Squad let him go with a new Alias.<br><br>
A few days later he was caught again for a similar crime, and was again awarded death , but this time no one asked his wish.<br><br>
<B>the code ! ! !</B><br><br><hr>
<FONT SIZE=3 COLOR="#3300FF">
<KBD>
public class MainClass{<br>
public static void main(String arg[]){<br><br>
System.out.println("In the beginning there was .... \n");<br>
Criminal Rambo=new Criminal();<br>
Rambo.showIDcard("Rambo");<br>
Criminal BigCat= Rambo; //Alias<br>
BigCat.showIDcard("BigCat");<br>
Rambo.doCrime();<br>
System.out.println("Waiting of justice.... ");<br>
Rambo=null;<br>
BigCat=null;<br>
System.gc();<br>
Criminal.TheRock.showIDcard("TheRock"); <br>
Criminal.TheRock.doCrime(); <br>
System.out.println("Waiting of justice.... ");<br>
Criminal.TheRock=null; <br>
System.gc();<br>
System.out.println("Criminal put to death without final wish ! ");<br>
}<br>
}<br>
<br><br>
class Criminal {<br>
<br>
public static Criminal TheRock; <br>
<br>
public Criminal(){System.out.println("Criminal born ! ");}<br>
<br>
public void showIDcard(String Alias){<br>
System.out.println(Alias +" ID: "+this.hashCode());<br>
}<br>
public void doCrime(){<br>
System.out.println("Criminal on rampage, Killed an innocent Object ");<br>
}<br>
<br>
public void finalize(){<br>
System.out.println("Verdict: Death penalty ");<br>
System.out.println("Criminal's last wish : resurrection !!! " ); <br>
TheRock=this;<br>
System.out.println("Criminal given a new refrence: TheRock ");<br>
throw new RuntimeException();<br>
} <br>
}<br>
 <br>
<hr></FONT>
<B>Out Put........</B><br><br>
In the beginning there was ....<br>
Criminal born !<br>
Rambo ID: 15347198<br>
BigCat ID: 15347198<br>
Criminal on rampage, Killed an innocent Object<br>
Waiting of justice....<br>
Verdict: Death penalty<br>
Criminal's last wish : resurrection !!!<br>
Criminal given a new refrence: TheRock<br>
TheRock ID: 15347198<br>
Criminal on rampage, Killed an innocent Object<br>
Waiting of justice....<br>
Criminal put to death without final wish !<br>
</KBD>
<br>
<br><hr><br>
<B>Moral of the Story.</B><br>
<UL>
<LI>Garbage Collector (gc) clears unrefrenced objects from the heap.
	<LI>Every Object may define finilize(), executed just before the object is removed from the heap.
	<LI>gc is moody, it works on its own will, System.gc() method is just a request not a compulsion (1.4).
	<LI>It is not guaranteed that finilize() will be executed for an object, mostly it does, if it happens in the middle of a long execution.
	<LI>any uncaught Exception thrown in finilize() is ignored.
	<LI>if during finilize() of an unrefrenced object, it gets reffered to again (as above), then gc cannot not remove the object from heap.
	<LI>if the object escapes the finilize() once, then the second time the finilize() is not called, the object is remove directly.
	<LI>finilize() methods are not chained (they dont work like constructors), ie. sub class finilize() does not implicitly call super class finilize(), we have to explicitly call super.finilize();
</UL>
<HR><BR><BR><BR><Font face="Verdana" size=2 >
your comment / votes are the source of encouragement, so please. - <FONT COLOR="#339900"><B>Rafay.</B></FONT></FONT><BR>
<HR>

