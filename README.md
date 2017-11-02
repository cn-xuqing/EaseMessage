# EaseMessage
  此类可进行对象的跨类，跨线程发送，有利于数据的快速传输。<br>
  有以下几个作用：<br>
 * 可以进行类之间数据传递<br>
 * 可以在不同的线程间进行数据传递<br>
 * 可以方便的实现应用内远程数据传递，可以少量代替使用广播发送数据
 # 调用非常的简单
 ```
 public class Demo {
	public Demo(){
		//发送
		EasyMessage.sendMessage("flag", "Demo");
		
		//接收
		EasyMessage.registerMessageListener("flag", mListener);
	}
	
	//处理消息
	public OnMessageListener mListener =new OnMessageListener() {
		public void onMessage(Object msg) { 
			System.out.println(msg+"");//打印Demo
		}
	};
	
	//当不需要时一定要调用unregisterMessageListener方法
	public void Distory(){
		//取消接收
		EasyMessage.unregisterMessageListener(mListener);
	}
}
```
