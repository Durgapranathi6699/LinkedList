//for palindrome reverse from half i.e from mid and check from rev and head till rev not null
//2nd approch can be using stack which stores reverse of numbers

 //  Stack<Integer> s=new Stack<>();
        // ListNode temp=head;
        // while(temp!=null){
        //     s.push(temp.val);
        //     temp=temp.next;
        // }
        // temp=head;
        // while(!s.empty() && temp!=null){
        //     if(s.pop()!=temp.val){
        //         return false;
        //     }
        //     temp=temp.next;
        // }
        // return true;
        ListNode mid=middle(head);
        ListNode rev=reverse(mid);
        while(rev!=null){
            if(rev.val!=head.val){
                return false;
            }
            rev=rev.next;
            head=head.next;
        }
        return true;
    }
    ListNode middle(ListNode head){
        ListNode slow=head;
        ListNode fast=head;
        while(fast!=null && fast.next!=null){
            slow=slow.next;
            fast=fast.next.next;
        }
        return slow;
    }
    ListNode reverse(ListNode head){
        ListNode pre=null;
        ListNode cur=head;
        ListNode curnext;
        while(cur!=null){
            curnext=cur.next;
            cur.next=pre;
            pre=cur;
            cur=curnext;
        }
        return pre;
