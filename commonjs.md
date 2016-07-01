
### 相关的正则表达式

<pre>function LEMONUtils() {}
isPassword : function(s) {
        return /(?!^[0-9]+$)(?!^[A-z]+$)(?!^[^A-z0-9]+$)^.{6,20}$/.test(s);
    },
    //邮箱验证
    isEmail : function(s) {
        var isEmailText = /^(?=\w+([-+.']\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*$).{0,30}$/;
        return isEmailText.test(s);
    },
    //校验手机号码
    isMobile : function(s) {
        var re=/^1[3-8]\d{9}$/;
        return re.test(s);
    },
    //校验邮政编码
    isZipCode : function(s) {
        var re = /^[1-9][0-9]{5}$/;
        return re.test(s);
    },
    isNumber:function(s) {
        var re = /^[0-9]*$/;
        return re.test(s);
    },
    isQQ:function(s) {
        var re = /^[1-9]*$/;
        return re.test(s);
    },
    isNickname:function(s){
        var re =/^[\u4E00-\u9FA5]{2,5}$/;
        return re.test(s);
    },
    //是否为金额
    isMoney: function(s) {
        var re = /^\d*(\.\d{1,2})?$|^\d*\.(\d{1,2})?$/;
        return re.test(s);
    },
    // 身份证
    isIdCard: function(idCard) {
        //15位和18位身份证号码的正则表达式
        var regIdCard = /^(^[1-9]\d{7}((0\d)|(1[0-2]))(([0|1|2]\d)|3[0-1])\d{3}$)|(^[1-9]\d{5}[1-9]\d{3}((0\d)|(1[0-2]))(([0|1|2]\d)|3[0-1])((\d{4})|\d{3}[Xx])$)$/;

        //如果通过该验证，说明身份证格式正确，但准确性还需计算
        if (regIdCard.test(idCard)) {
            if (idCard.length == 18) {
                var idCardWi = new Array(7, 9, 10, 5, 8, 4, 2, 1, 6, 3, 7, 9, 10, 5, 8, 4, 2); //将前17位加权因子保存在数组里
                var idCardY = new Array(1, 0, 10, 9, 8, 7, 6, 5, 4, 3, 2); //这是除以11后，可能产生的11位余数、验证码，也保存成数组
                var idCardWiSum = 0; //用来保存前17位各自乖以加权因子后的总和
                for (var i = 0; i < 17; i++) {
                    idCardWiSum += idCard.substring(i, i + 1) * idCardWi[i];
                }

                var idCardMod = idCardWiSum % 11; //计算出校验码所在数组的位置
                var idCardLast = idCard.substring(17); //得到最后一位身份证号码

                //如果等于2，则说明校验码是10，身份证号码最后一位应该是X
                if (idCardMod == 2) {
                    if (idCardLast == 'X' || idCardLast == 'x') {
                        return true;
                    } else {

                        return false;
                    }
                } else {
                    //用计算出的验证码与最后一位身份证号码匹配，如果一致，说明通过，否则是无效的身份证号码
                    if (idCardLast == idCardY[idCardMod]) {
                        return true;
                    } else {
                        return false;
                    }
                }
            }
        } else {
            return false;
        }
        return true;
    }
</pre>



