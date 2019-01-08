#DEMO
## 1. 借款服务合同接口
### GET /v2/contract/loan/{sn}
### Response说明

字段名 | 说明 | 类型
---|---|---
contractSn | 合同编号 | String
signDate | 签订日期 | String
loanName | 借款人名字 | String
loanIdCard | 借款人身份证 | String
loanMobile | 借款人手机号 | String
loanCardNo | 借款人银行卡号 | String
principal | 本金 | String
periods | 借款期数 | String
loanDate | 借款时间 | String
loanEndDate | 借款结束时间 | String
serviceFee | 乙方服务费 | String
otherServiceFee | 丙方服务费 | String
creditAmount | 放款金额 | String
creditServiceFee | 放款服务费 | String
repaymentMonth | 还款金额 | String
repaymentPrincipal | 还款本金 | String
repaymentServiceFee | 还款服务费 | String
overdueFee | 逾期罚息 | String


### 格式--成功：


```
{
    "code":200,
    "message":"",
    "data": {
        "contractSn":"",
        "signDate":"",
        "loanName":"",
        "loanIdCard":"",
        "loanMobile":"",
        "loanCardNo":"",
        "principal":"",
        "periods":"",
        "loanDate":"",
        "loanEndDate":"",
        "serviceFee":"",
        "otherServiceFee":"",
        "creditAmount":"",
        "creditServiceFee":"",
        "repaymentMonth":"",
        "repaymentPrincipal":"",
        "repaymentServiceFee":"",
        "overdueFee":""
    }
}
```


## 2. 担保协议
### GET /v2/contract/agreement/{sn}
### Response说明

字段名 | 说明 | 类型
---|---|---
loanContractSn | 借款合同编号 | String
contractSn | 合同编号 | String
signDate | 签订日期 | String
loanName | 借款人名字 | String
loanIdCard | 借款人身份证 | String
loanMobile | 借款人手机号 | String



### 格式--成功：


```
{
    "code":200,
    "message":"",
    "data": {
        "loanContractSn":"",
        "contractSn":"",
        "signDate":"",
        "loanName":"",
        "loanIdCard":"",
        "loanMobile":""
    }
}
```


