Gradle ��������
	��groovy����д�� groovy���ձ�������ֽ����ļ���.class�� Ȼ��������jVM  java�������
	
	groovy��һЩ�����﷨
		ע�ͺ�javaһ�� ֧�� // �� /* */
		��䲻��Ҫ�ֺŽ�β
		֧�ֶ�̬���� ���������ʱ����Բ�ָ������ ����ʹ��def�ؼ���  def�ؼ���Ҳ���Ǳ����
				eg: def var1 = 1
					def var2 = 'hello world';
		����������Ҳ���Բ�ָ��
		�����ķ���ֵҲ�����������͵� �����Ͷ���ķ���ֵ���� ����ʹ��def�ؼ��� ���һ�����ķ���ֵ���Ǳ������ķ���ֵ return
		
		
	groovy����������
		java������������
				��Groovy��������ʵ��Ӧ�������ǵİ�װ�������͡�����int��ӦΪInteger��boolean��ӦΪBoolean
		java��������������
		
				list������ �ײ��Ӧjava��list�ӿ� һ����arraylistʵ��֮
						�������壺List������[]���壬����  
						def aList = [5,'string',true] //List��[]���壬��Ԫ�ؿ������κζ���  
						������ȡ������ֱ��ͨ��������ȡ�����Ҳ��õ�������Խ�硣�������������ǰ�����ȣ�List���Զ�  
						�����������Ԫ��  
						assert aList[1] == 'string'  
						assert aList[5] == null //��6��Ԫ��Ϊ��  
						aList[100] = 100 //���õ�101��Ԫ�ص�ֵΪ10  
						assert aList[100] == 100  
						��ô��aList������Ϊֹ�ж��ٸ�Ԫ���أ�  
						println aList.size  ===>�����101  


				map����ֵ�� 
						�������壺Map������[:]���壬����  
						def aMap = ['key1':'value1','key2':true]  
						Map��[:]���壬ע�����е�ð�š�ð�������key���ұ���Value��key�������ַ�����value�������κζ������⣬key������''��""��������Ҳ���Բ������Ű�����������  
						def aNewMap = [key1:"value",key2:true]//���е�key1��key2Ĭ�ϱ�  
						������ַ���"key1"��"key2"  
						����KeyҪ�ǲ�ʹ�����Ű������Ļ���Ҳ�����һ������������  
						def key1="wowo"  
						def aConfusedMap=[key1:"who am i?"]  
						aConfuseMap�е�key1������"key1"���Ǳ���key1��ֵ��wowo������Ȼ�������ַ���"key1"�����Ҫ��"wowo"�Ļ�����aConfusedMap�Ķ���������óɣ�  
						def aConfusedMap=[(key1):"who am i?"]  
						Map��Ԫ�صĴ�ȡ���ӷ��㣬��֧�ֶ��ַ�����  
						println aMap.keyName    <==���ֱ�﷽������key����aMap��һ����Ա����һ��  
						println aMap['keyName'] <==���ֱ�﷽������ͳһ��  
						aMap.anotherkey = "i am map"  <==Ϊmap�����Ԫ�� 
										
		

				Range����Χlist��һ����չ
					def aRange = 1..5 <==Range���͵ı��� ��beginֵ+������+endֵ��ʾ  
                      ������aRange����1,2,3,4,5��5��ֵ  
						�������������һ��Ԫ�أ���  
						def aRangeWithoutEnd = 1..<5  <==����1,2,3,4��4��Ԫ��  
						println aRange.from  
						println aRange.to  
			
		�հ�
			Ӣ����closure 
				deg aClosure = {
					String param1��int param2 ->
					return param1 +int 
				}
				
			���ñհ��ķ�ʽ:
						aClosure.call("dddddd",100);
						aClosure("dddddd",100);
						
						
			����հ�û��������Ļ�����������һ������������������ֽ�it����this���������ơ�it����հ��Ĳ�����

						���磺  
						def greeting = { "Hello, $it!" }  
						assert greeting('Patrick') == 'Hello, Patrick!'  
						��ͬ�ڣ�  
						def greeting = { it -> "Hello, $it!"}  
						assert greeting('Patrick') == 'Hello, Patrick!'  
						���ǣ�����ڱհ�����ʱ��������������д�������ʾ�հ�û�в�����  
						def noParamClosure = { -> true }  
						���ʱ�����ǾͲ��ܸ�noParamClosure�������ˣ�  
						noParamClosure ("test")  <==����ร�  
						
						
						
						
						
						
						