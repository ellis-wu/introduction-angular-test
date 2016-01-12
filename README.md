# 介紹 AngularJS 

> 參考文獻：[前端自動化測試工具總結](https://github.com/kuangwk/myblog/issues/1)

簡單介紹 AngularJS 測試工具與一些比較，若有錯誤，歡迎指教。

# TDD vs BDD

#### 測試驅動開發(Test-Drivin Development, TDD)
為一種程式開發的技巧，先撰寫```測試程式```，然後才實作功能。讓測試來驅動整個專案進行，先規劃測試並撰寫測試後在撰寫功能，並不斷進行測試使其通過，最後使所有測試均通過以完成本次開發。

> 參考文獻：[程式設計師升級必練內功：TDD Kata](https://blog.alphacamp.co/2015/03/02/tdd-kata/)

#### 行為驅動開發(Behavior-Drivin Development, BDD)
常有人說 BDD 為一種替代 TDD 的方法，而 BDD 是一種自動化測試方法論，注重以```通用語言```表達測試，以便於整個團隊在討論問題時分享。BDD 透過 DSL(Domain-specific language)來描述系統的行為，透過屬於該 Domain 的表達方式，來描述系統的特徵或功能與使用者的情境(Scenario)，並依據情境產生對應的 code flow template，接著可結合 Unit Test 來驗證系統功能是否有滿足這些情境(Scenario)。

> 參考文獻：[30天快速上手 TDD Day 23 - BDD - Introduction](https://msdn.microsoft.com/zh-tw/library/dn308251.aspx)

# 前端測試工具簡單整理和比較

### Karma
Angular 團隊開發的測試環境，可支持多種設備測試，且可在它之上搭配```Jasmine```、```Mocha```等測試工具。

### PhantomJS
為無介面的```Webkit``` Kernel 瀏覽器，提供一系列操作介面的 API，可以在節點上操作真實的瀏覽器介面。

### [Jasmine](http://jasmine.github.io/2.0/introduction.html) vs [Mocha](https://mochajs.org/)
皆為測試框架，而出現的時間順序為```Jasmin``` -> ```Mocha```。以下將比較兩者優缺點。

> 可參考：
> 1. [Which JavaScript Test Library Should You User? QUnit vs Jasmine vs Mocha](http://www.techtalkdc.com/which-javascript-test-library-should-you-use-qunit-vs-jasmine-vs-mocha/)
> 2. [Comparison of three major javascript unit testing frameworks](https://github.com/thegrtman/javascript-test-framework-comparison)

##### Mocha
* 優點：
	* 配置簡單
	* 終端顯示友好
	* 自身同時支持```Node.js```跟```broswer```
	* 擴展性佳
	* 擁有更好的 BDD 和 TDD 導向功能的 libraries
* 缺點：
	* 沒有```spy```與```斷言```，但可搭配[sinon](http://sinonjs.org/docs/#sinonspy)與[chi](http://chaijs.com/)

##### Jasmine
* 優點：
	* 為一 BDD/TDD 框架
	* 配置方便
	* 主打 Broswer 端，介面風格清新
	* 內建```斷言```語法
* 缺點：
	* 雖內建```斷言```語法，但無法與其他```斷言 libraries```配合得很好。
	* 異步測試不佳
	* 自身不支持```node.js```，要借助第三方工具 [jasmine-node](https://github.com/mhevery/jasmine-node)，因此有版本迭代跟不上的問題
	* 終端顯示較不友好
