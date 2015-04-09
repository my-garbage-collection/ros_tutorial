#!/usr/bin/env python
# license removed for brevity
import rospy
from std_msgs.msg import String
from original_msgs.msg import OriginalMsg
import time

def talker():
    pub = rospy.Publisher('chatter', String, queue_size=10)
    pub_original = rospy.Publisher('original_data', OriginalMsg, queue_size=10)
    rospy.init_node('talker', anonymous=True)
    
    data = OriginalMsg()
    # r = rospy.Rate(0.5) # 10hz
    while not rospy.is_shutdown():
    # while True:
        str = "hello world %s"%rospy.get_time()
        rospy.loginfo(str)
        pub.publish(str)
        data.is_ok = True
        # data.data = 10
        data.arr.append(1)
        pub_original.publish(data)
        time.sleep(1)
        # r.sleep()

if __name__ == '__main__':
    try:
        talker()
    except rospy.ROSInterruptException: pass
