帮我写一段python代码，实现如下功能。

## 输入示例
**注意**：下面只是一个输入的示例，内容可能并不完整
```
[
  {
    "name": "input",
    "value": "{\"content\":[{\"type\":\"text\",\"text\":\"{\\\"resultCode\\\":0,\\\"success\\\":true,\\\"resultMsg\\\":\\\"成功\\\",\\\"result\\\":{\\\"applyId\\\":0,\\\"newApplyId\\\":172725276709492276,\\\"orderId\\\":5008028991768250932,\\\"productCode\\\":57,\\\"refundQuantity\\\":1,\\\"refundAmount\\\":1069.0,\\\"applyStatus\\\":\\\"0004\\\",\\\"statusDescription\\\":\\\"退款完成\\\",\\\"displayStatus\\\":3,\\\"refundDestination\\\":2,\\\"refundPlatform\\\":20050400,\\\"refundTemplateId\\\":2000001,\\\"userId\\\":2384924617,\\\"operatorType\\\":0,\\\"operatorId\\\":0,\\\"productId\\\":0,\\\"longProductId\\\":0,\\\"productGroupId\\\":0,\\\"longProductGroupId\\\":0,\\\"addTime\\\":1760372679635,\\\"updateTime\\\":1760372689000,\\\"successTime\\\":1760372679000,\\\"refundReason\\\":\\\"支付确认失败\\\",\\\"errorCode\\\":0,\\\"refundAmountModelType\\\":0,\\\"unifiedOrderId\\\":\\\"5008028991768250932\\\",\\\"merchantAffordAmount\\\":0.0,\\\"refundId\\\":0,\\\"refundTargetList\\\":[{\\\"targetVoucher\\\":\\\"25101411100301670008711100462766\\\",\\\"targetType\\\":\\\"BUY_FAIL\\\",\\\"targetTypeDesc\\\":\\\"购买失败\\\"}],\\\"extraInfo\\\":{},\\\"bizType\\\":90,\\\"operationLogList\\\":[{\\\"operatorName\\\":\\\"系统\\\",\\\"operatorId\\\":\\\"0\\\",\\\"operatorType\\\":4,\\\"actionType\\\":1,\\\"operationTime\\\":1760372680000},{\\\"operatorName\\\":\\\"系统\\\",\\\"operatorId\\\":\\\"0\\\",\\\"operatorType\\\":4,\\\"actionType\\\":2,\\\"operationTime\\\":1760372680000}]}}\"}],\"isError\":false}"
  }
]
```

## 期望输出
从输入中提取出如下结构：
```
{
    "updateTime": {
        "desc": "最后更新时间",
        "value": "2025-10-14 00:24:49"
    },
    "applyStatus": {
        "desc": "退款单状态，0001退款申请已创建,0002退款取消,0003退款确认, 0004退款完成,0005对不起退款失败,0006退款审核中,0007退款审核成功", 
        "value": "0004"
    },
    "statusDescription": {
        "desc": "状态描述", 
        "value": "退款完成"
    },
    "addTime": {
        "desc": "退款发起时间",
        "value": "2025-10-14 00:24:39"
    },
    "successTime": {
        "desc": "成功时间",
        "value": "2025-10-14 00:24:39"
    },
    "refundReason": {
        "desc": "退款原因",
        "value": "支付确认失败"
    },
    "refundTemplateId": {
        "desc": "退款模板",
        "value": 2000001
    },
    "newApplyId": {
        "desc": "退款申请单id",
        "value": "172725276709492276"
    },
    "operationLogList": {
        "desc": "退款操作流程",
        "value": [
            {
                "actionType": {
                    "desc": "操作类型，1申请退款,2退款审核通过,3退款审核拒绝,4取消退款,5回写退款原因", 
                    "value": "1"
                },
                "operationTime": {
                    "desc": "操作时间",
                    "value": "2025-10-14 00:24:40"
                },
                "operatorId": {
                    "desc": "操作人ID",
                    "value": "0"
                },
                "operatorName": {
                    "desc": "操作人名称", 
                    "value": "系统"
                },
                "operatorType": {
                    "desc": "操作人类型，1美团用户中心账号,2商家账号,3员工账号,4系统,5点评用户中心账号",
                    "value": 4
                },
                "remark": {
                    "desc": "备注",
                    "value": null
                },
                "source": {
                    "desc": "来源",
                    "value": null
                }
            }
        ]
    }
}
```

## 代码模板
```
# 定义一个 main 函数，传入 params 参数。params 中包含了节点配置的输入变量。
# 需要定义一个字典作为输出变量
# 引用节点定义的变量：params['变量名']
# 运行环境 Python3；预置 Package：NumPy

def main(params:dict) -> dict:

    # 创建一个字典作为输出变量
    output_object ={
    
        # 引用节点定义的 input 变量
        "key0": params['input'], 

        # 为 “key1” 赋值一个字符串数组
        "key1": ["hello", "world"],

        # 为 “key2" 赋值一个字典，包含多种类型数据
        "key2": {
            "key21": "hi"
        }
    }

    # 返回输出字典类型变量 output_object，包含代码节点所需的输出数据
    return output_object
```

**注意**：“## 期望输出”中规定的结构不是代码中的output_object，而是output_object里的一个item，key为extracted_data