创建自己的dex，并添加流动性。

# Ropsten测试网
我的地址：0xC8b7a5561e29E7Cf36ed970cc73D9E37da3EB823

## 1.部署Core
Core(Factory Pair) 合约地址：0x9069bb0717ce976c03ee76f65c30f01719bda09b

## 2.部署WETH和DAI
WETH：0x24564639ef1615887f23fefb2265289220894139
DAI : 0x2c3af037312ab82a367799c27e3d4e7263c0f04d


## 3.Create Pair(WETH/DAI) (可选，没有交易对时使用router的addLiquidityETH会直接创建)
pair: 0xC556aDEf218Fa049adf41CE08F16Dd9b7408Be65


## 4.部署UniswapV2Router02
router02地址：0x38811859AF5cd7f80340F4e4A4a75b41C5376Cd5

记得https://remix.ethereum.org/#optimize=true设置位false，否则router合约会超限

注意：
- pairFor方法里面的init code hash 更改成正确的值。
- create2 address 计算方法: keccak256 (0xff + address + salt +  init code hash)
- address：即为调用create2的合约地址，此处即factory地址
- init code hash：即pair合约字节码的hash ，即keccak256(type(UniswapV2Pair).creationCode)
         

## 5.addLiquidityETH
add前先给router approve一下相应数量的Dai.
增加流动性的tx
https://ropsten.etherscan.io/tx/0x2d5e73a53bf9255e8f57e0f38cff0fa8328e873a440cd439c667bd9880e600ee


## 6.swap ETH/DAI



## truffle test：

https://github.com/OK0X/uniswapv2-router2

https://github.com/OK0X/uniswapv2-factory
