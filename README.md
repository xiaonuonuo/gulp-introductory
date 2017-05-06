# gulp-
gulp详细入门教程

<div class="main-margin">
    <header class="detail-titile"><h2>gulp详细入门教程</h2></header>
    <div class="excerpt"><h3>简介：</h3>
        <p>
            gulp是前端开发过程中对代码进行构建的工具，是自动化项目的构建利器；她不仅能对网站资源进行优化，而且在开发过程中很多重复的任务能够使用正确的工具自动完成；使用她，我们不仅可以很愉快的编写代码，而且大大提高我们的工作效率。</p>
    </div>
    <article class="detail-concent clearfix"><p class="ti2">gulp是基于Nodejs的自动任务运行器， 她能自动化地完成
        javascript/coffee/sass/less/html/image/css
        等文件的的测试、检查、合并、压缩、格式化、浏览器自动刷新、部署文件生成，并监听文件在改动后重复指定的这些步骤。在实现上，她借鉴了Unix操作系统的管道（pipe）思想，前一级的输出，直接变成后一级的输入，使得在操作上非常简单。通过本文，我们将学习如何使用Gulp来改变开发流程，从而使开发更加快速高效。</p>
        <p class="ti2" style="margin-top: 10px;">gulp 和 grunt 非常类似，但相比于 grunt 的频繁 IO 操作，gulp 的流操作，能更快地更便捷地完成构建工作。</p>
        <p style="margin: 20px 0; text-indent: 2em;">
            本示例以gulp-less为例（将less编译成css的gulp插件）展示gulp的常规用法，只要我们学会使用一个gulp插件后，其他插件就差看看其帮助文档了。让我们一起来学习gulp吧！ ^_^</p>
        <p>gulp常用地址：</p>
        <p class="ti2">gulp官方网址：<a href="//gulpjs.com/" target="_blank">http://gulpjs.com</a></p>
        <p class="ti2">gulp插件地址：<a href="//gulpjs.com/plugins" target="_blank">http://gulpjs.com/plugins</a></p>
        <p class="ti2">gulp 官方API：<a href="https://github.com/gulpjs/gulp/blob/master/docs/API.md" target="_blank">https://github.com/gulpjs/gulp/blob/master/docs/API.md</a>
        </p>
        <p class="ti2">gulp 中文API：<a href="424" target="_blank">http://www.ydcss.com/archives/424</a></p>
        <p style="margin-top: 20px;">目录：</p>
        <div class="index-box1" style="line-height: 28px;">
            <div class="f"><a href="#lesson1">1、安装nodejs</a></div>
            <div class="f"><a href="#lesson2">2、使用命令行</a></div>
            <div class="f"><a href="#lesson3">3、npm介绍</a></div>
            <div class="f"><a href="#lesson4">4、选装cnpm</a></div>
            <div class="f"><a href="#lesson5">5、全局安装gulp</a></div>
            <div class="f"><a href="#lesson6">6、新建package.json文件</a></div>
            <div class="f"><a href="#lesson7">7、本地安装gulp插件</a></div>
            <div class="f"><a href="#lesson8">8、新建gulpfile.js文件</a></div>
            <div class="f"><a href="#lesson9">9、运行gulp</a></div>
            <div class="f"><a href="#lesson10">10、使用webstorm运行gulp任务</a></div>
            <div class="f"><a href="#lesson11">11、总结</a></div>
        </div>
        <p style="margin-top: 20px; text-indent: 2em; font-size: 16px; line-height: 30px;">
            在学习前，先谈谈大致使用gulp的步骤，给读者以初步的认识。首先当然是安装nodejs，通过nodejs的npm全局安装和项目安装gulp，其次在项目里安装所需要的gulp插件，然后新建gulp的配置文件gulpfile.js并写好配置信息（定义gulp任务），最后通过命令提示符运行gulp任务即可。</p>
        <p style="margin-bottom: 10px; text-indent: 2em; font-size: 16px; line-height: 30px; color: #555; font-weight: bold;">
            安装nodejs -&gt; 全局安装gulp -&gt; 项目安装gulp以及gulp插件 -&gt; 配置gulpfile.js -&gt; 运行任务</p>
        <h3 id="lesson1">1、安装nodejs</h3>
        <p class="ti15">1.1、说明：gulp是基于nodejs，理所当然需要安装nodejs；</p>
        <p class="ti15">1.2、安装：打开<a href="//nodejs.org/" target="_blank">nodejs官网</a>，点击硕大的绿色Download按钮，它会根据系统信息选择对应版本（.msi文件）。然后像安装QQ一样安装它就可以了（安装路径随意）。
        </p>
        <h3 id="lesson2">2、使用命令行（如果你熟悉命令行，可以直接跳到<a href="18#lesson3">第3步</a>）</h3>
        <p class="ti15">2.1、说明：什么是命令行？命令行在OSX是终端（Terminal），在windows是命令提示符（Command Prompt）；</p>
        <p class="ti15">2.2、注：之后操作都是在windows系统下；</p>
        <p class="ti15">2.3、简单介绍gulp在使用过程中常用命令，打开命令提示符执行下列命令（打开方式：window&nbsp;+ r 输入cmd回车）：</p>
        <p class="ti3"><strong style="margin-right: 5px;">node -v</strong>查看安装的nodejs版本，出现版本号，说明刚刚已正确安装nodejs。PS：未能出现版本号，请尝试注销电脑重试；
        </p>
        <p class="ti3"><strong style="margin-right: 5px;">npm -v</strong>查看npm的版本号，npm是在安装nodejs时一同安装的nodejs包管理器，那它有什么用呢？<a
                href="#lesson3">稍后解释</a>；</p>
        <p class="ti3"><strong style="margin-right: 5px;">cd</strong>定位到目录，用法：cd + 路径 ；</p>
        <p class="ti3"><strong style="margin-right: 5px;">dir</strong>列出文件列表；</p>
        <p class="ti3"><strong style="margin-right: 5px;">cls</strong>清空命令提示符窗口内容。</p>
        <p class="ti3"><img src="http://static.ydcss.com/uploads/2015/03/gulp-01.png" alt=""
                            data-url="http://static.ydcss.com/uploads/2015/03/gulp-01.png"></p>
        <h3 id="lesson3">3、npm介绍</h3>
        <p class="ti15">3.1、说明：npm（node package manager）nodejs的包管理器，用于node插件管理（包括安装、卸载、管理依赖等）；</p>
        <p class="ti15">3.2、使用npm安装插件：命令提示符执行<strong class="cmd"><code>npm install &lt;name&gt; [-g] [--save-dev]</code></strong>；
        </p>
        <p class="ti3">3.2.1、<strong style="margin-right: 5px;">&lt;name&gt;</strong>：node插件名称。例：<strong
                class="cmd"><code>npm install gulp-less --save-dev</code></strong></p>
        <p class="ti3">3.2.2、<strong style="margin-right: 5px;">-g</strong>：全局安装。将会安装在<code>C:\Users\Administrator\AppData\Roaming\npm</code>，并且写入系统环境变量；
            &nbsp;非全局安装：将会安装在当前定位目录； &nbsp;全局安装可以通过命令行在任何地方调用它，本地安装将安装在定位目录的node_modules文件夹下，通过require()调用；</p>
        <p class="ti3">3.2.3、<strong style="margin-right: 5px;"><code>--save</code></strong>：将保存配置信息至package.json（package.json是<a
                href="18#lesson6">nodejs项目配置文件</a>）；</p>
        <p class="ti3">3.2.4、<strong style="margin-right: 5px;">-dev</strong>：保存至package.json的devDependencies节点，不指定-dev将保存至dependencies节点；
        </p>
        <p id="why" class="ti3" style="padding-top: 90px; margin-top: -85px;">
            3.2.5、为什么要保存至package.json？因为node插件包相对来说非常庞大，所以不加入版本管理，将配置信息写入package.json并将其加入版本管理，其他开发者对应下载即可（命令提示符执行<strong
                class="cmd">npm install</strong>，则会根据package.json下载所有需要的包）。</p>
        <p class="ti15">3.3、使用npm卸载插件：<strong class="cmd"><code>npm uninstall &lt;name&gt; [-g]
            [--save-dev]</code></strong> &nbsp;PS：不要直接删除本地插件包</p>
        <p class="ti15">3.4、使用npm更新插件：<strong class="cmd">npm update &lt;name&gt; [-g] <code>
            [--save-dev]</code></strong></p>
        <p class="ti3">3.4.1、更新全部插件：<strong class="cmd">npm update<code> [--save-dev]</code></strong></p>
        <p class="ti15">3.5、查看npm帮助：<strong class="cmd">npm help</strong></p>
        <p class="ti15">3.6、当前目录已安装插件：<strong class="cmd">npm list</strong></p>
        <p class="ti15" style="font-weight: 800;">
            PS：npm安装插件过程：从http://registry.npmjs.org下载对应的插件包（该网站服务器位于国外，所以经常下载缓慢或出现异常），解决办法往下看↓↓↓↓↓↓。</p>
        <h3 id="lesson4">4、选装cnpm</h3>
        <p class="ti15">4.1、说明：因为npm安装插件是从国外服务器下载，受网络影响大，可能出现异常，如果npm的服务器在中国就好了，所以我们乐于分享的淘宝团队干了这事。<span
                style="color: #ff5d50;">32个<i class="iconfont" style="font-size: 15px; margin-left: 4px;"></i></span>！来自官网：<strong>“这是一个完整
            npmjs.org 镜像，你可以用此代替官方版本(只读)，同步频率目前为 10分钟 一次以保证尽量与官方服务同步。”</strong>；</p>
        <p class="ti15">4.2、官方网址：<a href="//npm.taobao.org/" target="_blank">http://npm.taobao.org</a>；</p>
        <p class="ti15">4.3、安装：命令提示符执行<strong class="cmd"><code>npm install cnpm -g
            --registry=https://registry.npm.taobao.org</code></strong>； &nbsp;注意：安装完后最好查看其版本号<strong class="cmd">cnpm
            -v</strong>或关闭命令提示符重新打开，安装完直接使用有可能会出现错误；</p>
        <p class="ti15">注：cnpm跟npm用法完全一致，只是在执行命令时将npm改为cnpm（以下操作将以cnpm代替npm）。</p>
        <h3 id="lesson5">5、全局安装gulp</h3>
        <p class="ti15">5.1、说明：全局安装gulp目的是为了通过她执行gulp任务；</p>
        <p class="ti15">5.2、安装：命令提示符执行<strong class="cmd">cnpm install gulp -g</strong>；</p>
        <p class="ti15">5.3、查看是否正确安装：命令提示符执行<strong class="cmd">gulp -v</strong>，出现版本号即为正确安装。</p>
        <h3 id="lesson6">6、新建package.json文件</h3>
        <p class="ti15">6.1、说明：package.json是基于nodejs项目必不可少的配置文件，它是存放在项目根目录的普通json文件；</p>
        <p class="ti15">6.2、它是这样一个json文件<strong style="color: #f00;">（注意：json文件内是不能写注释的，复制下列内容请删除注释）</strong>：</p>
        <div class="code-box">
            <link rel="stylesheet" type="text/css"
                  href="/wp-content/plugins/crayon-syntax-highlighter/fonts/consolas.css">
            <div id="crayon-5726fb0698d89156248850"
                 class="crayon-syntax crayon-theme-raygun crayon-font-consolas crayon-os-pc print-yes notranslate"
                 data-settings=" minimize scroll-mouseover"
                 style=" margin-bottom: 12px; font-size: 14px !important; line-height: 18px !important;">
                <div class="crayon-toolbar" data-settings=" show"
                     style="font-size: 14px !important;height: 21px !important; line-height: 21px !important;"><span
                        class="crayon-title"></span>
                    <div class="crayon-tools"
                         style="font-size: 14px !important;height: 21px !important; line-height: 21px !important;">
                        <div class="crayon-button crayon-nums-button" title="切换是否显示行编号">
                            <div class="crayon-button-icon"></div>
                        </div>
                        <div class="crayon-button crayon-wrap-button" title="切换自动换行">
                            <div class="crayon-button-icon"></div>
                        </div>
                        <div class="crayon-button crayon-expand-button" title="点击展开代码">
                            <div class="crayon-button-icon"></div>
                        </div>
                        <div class="crayon-button crayon-popup-button" title="在新窗口中显示代码">
                            <div class="crayon-button-icon"></div>
                        </div>
                        <span class="crayon-language">JavaScript</span></div>
                </div>
                <div class="crayon-info" style="min-height: 19.6px !important; line-height: 19.6px !important;"></div>
                <div class="crayon-plain-wrap"></div>
                <div class="crayon-main">
                    <table class="crayon-table">
                        <tbody>
                        <tr class="crayon-row">
                            <td class="crayon-nums " data-settings="show">
                                <div class="crayon-nums-content"
                                     style="font-size: 14px !important; line-height: 18px !important;">
                                    <div class="crayon-num" data-line="crayon-5726fb0698d89156248850-1">1</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698d89156248850-2">2
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698d89156248850-3">3</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698d89156248850-4">4
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698d89156248850-5">5</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698d89156248850-6">6
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698d89156248850-7">7</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698d89156248850-8">8
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698d89156248850-9">9</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698d89156248850-10">10
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698d89156248850-11">11</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698d89156248850-12">12
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698d89156248850-13">13</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698d89156248850-14">14
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698d89156248850-15">15</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698d89156248850-16">16
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698d89156248850-17">17</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698d89156248850-18">18
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698d89156248850-19">19</div>
                                </div>
                            </td>
                            <td class="crayon-code">
                                <div class="crayon-pre"
                                     style="font-size: 14px !important; line-height: 18px !important; -moz-tab-size:4; -o-tab-size:4; -webkit-tab-size:4; tab-size:4;">
                                    <div class="crayon-line" id="crayon-5726fb0698d89156248850-1"><span
                                            class="crayon-sy">{</span></div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698d89156248850-2">
                                        <span class="crayon-h">&nbsp;&nbsp;</span><span
                                            class="crayon-s">"name"</span><span class="crayon-o">:</span><span
                                            class="crayon-h"> </span><span class="crayon-s">"test"</span><span
                                            class="crayon-sy">,</span><span class="crayon-h">&nbsp;&nbsp; </span><span
                                            class="crayon-c">//项目名称（必须）</span></div>
                                    <div class="crayon-line" id="crayon-5726fb0698d89156248850-3"><span
                                            class="crayon-h">&nbsp;&nbsp;</span><span
                                            class="crayon-s">"version"</span><span class="crayon-o">:</span><span
                                            class="crayon-h"> </span><span class="crayon-s">"1.0.0"</span><span
                                            class="crayon-sy">,</span><span class="crayon-h">&nbsp;&nbsp; </span><span
                                            class="crayon-c">//项目版本（必须）</span></div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698d89156248850-4">
                                        <span class="crayon-h">&nbsp;&nbsp;</span><span
                                            class="crayon-s">"description"</span><span class="crayon-o">:</span><span
                                            class="crayon-h"> </span><span class="crayon-s">"This is for study gulp project !"</span><span
                                            class="crayon-sy">,</span><span class="crayon-h">&nbsp;&nbsp; </span><span
                                            class="crayon-c">//项目描述（必须）</span></div>
                                    <div class="crayon-line" id="crayon-5726fb0698d89156248850-5"><span
                                            class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"homepage"</span><span
                                            class="crayon-o">:</span><span class="crayon-h"> </span><span
                                            class="crayon-s">""</span><span class="crayon-sy">,</span><span
                                            class="crayon-h">&nbsp;&nbsp; </span><span class="crayon-c">//项目主页</span>
                                    </div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698d89156248850-6">
                                        <span class="crayon-h">&nbsp;&nbsp;</span><span
                                            class="crayon-s">"repository"</span><span class="crayon-o">:</span><span
                                            class="crayon-h"> </span><span class="crayon-sy">{</span><span
                                            class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-c">//项目资源库</span>
                                    </div>
                                    <div class="crayon-line" id="crayon-5726fb0698d89156248850-7"><span
                                            class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"type"</span><span
                                            class="crayon-o">:</span><span class="crayon-h"> </span><span
                                            class="crayon-s">"git"</span><span class="crayon-sy">,</span></div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698d89156248850-8">
                                        <span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"url"</span><span
                                            class="crayon-o">:</span><span class="crayon-h"> </span><span
                                            class="crayon-s">"https://git.oschina.net/xxxx"</span></div>
                                    <div class="crayon-line" id="crayon-5726fb0698d89156248850-9"><span
                                            class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span
                                            class="crayon-sy">,</span></div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698d89156248850-10">
                                        <span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"author"</span><span
                                            class="crayon-o">:</span><span class="crayon-h"> </span><span
                                            class="crayon-sy">{</span><span
                                            class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-c">//项目作者信息</span>
                                    </div>
                                    <div class="crayon-line" id="crayon-5726fb0698d89156248850-11"><span
                                            class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"name"</span><span
                                            class="crayon-o">:</span><span class="crayon-h"> </span><span
                                            class="crayon-s">"surging"</span><span class="crayon-sy">,</span></div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698d89156248850-12">
                                        <span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"email"</span><span
                                            class="crayon-o">:</span><span class="crayon-h"> </span><span
                                            class="crayon-s">"surging2@qq.com"</span></div>
                                    <div class="crayon-line" id="crayon-5726fb0698d89156248850-13"><span
                                            class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span
                                            class="crayon-sy">,</span></div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698d89156248850-14">
                                        <span class="crayon-h">&nbsp;&nbsp;</span><span
                                            class="crayon-s">"license"</span><span class="crayon-o">:</span><span
                                            class="crayon-h"> </span><span class="crayon-s">"ISC"</span><span
                                            class="crayon-sy">,</span><span
                                            class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-c">//项目许可协议</span>
                                    </div>
                                    <div class="crayon-line" id="crayon-5726fb0698d89156248850-15"><span
                                            class="crayon-h">&nbsp;&nbsp;</span><span
                                            class="crayon-s">"devDependencies"</span><span
                                            class="crayon-o">:</span><span class="crayon-h"> </span><span
                                            class="crayon-sy">{</span><span
                                            class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-c">//项目依赖的插件</span>
                                    </div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698d89156248850-16">
                                        <span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"gulp"</span><span
                                            class="crayon-o">:</span><span class="crayon-h"> </span><span
                                            class="crayon-s">"^3.8.11"</span><span class="crayon-sy">,</span></div>
                                    <div class="crayon-line" id="crayon-5726fb0698d89156248850-17"><span
                                            class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"gulp-less"</span><span
                                            class="crayon-o">:</span><span class="crayon-h"> </span><span
                                            class="crayon-s">"^3.0.0"</span></div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698d89156248850-18">
                                        <span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span></div>
                                    <div class="crayon-line" id="crayon-5726fb0698d89156248850-19"><span
                                            class="crayon-sy">}</span></div>
                                </div>
                            </td>
                        </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
        <p class="ti15">6.3、当然我们可以手动新建这个配置文件，但是作为一名有志青年，我们应该使用更为效率的方法：命令提示符执行<strong class="cmd">cnpm init</strong></p>
        <p class="ti15" style="margin: 5px 0;"><img src="http://static.ydcss.com/uploads/2015/03/gulp-3.png" alt=""
                                                    data-url="http://static.ydcss.com/uploads/2015/03/gulp-3.png"></p>
        <p class="ti15">6.4、查看package.json帮助文档，命令提示符执行<strong class="cmd">cnpm help package.json</strong></p>
        <p class="ti15">特别注意：package.json是一个普通json文件，所以不能添加任何注释。参看 <a href="//www.zhihu.com/question/23004511"
                                                                      target="_blank">http://www.zhihu.com/question/23004511</a>
        </p>
        <h3 id="lesson7">7、本地安装gulp插件</h3>
        <p class="ti15">7.1、安装：定位目录命令后提示符执行<strong class="cmd"><code>cnpm install --save-dev</code></strong>；</p>
        <p class="ti15">7.2、本示例以gulp-less为例（编译less文件），命令提示符执行<strong class="cmd"><code>cnpm install gulp-less
            --save-dev</code></strong>；</p>
        <p class="ti15"><img src="http://static.ydcss.com/uploads/2015/02/gulp-less-2.png" alt=""
                             data-url="http://static.ydcss.com/uploads/2015/02/gulp-less-2.png"></p>
        <p class="ti15">7.3、将会安装在node_modules的gulp-less目录下，该目录下有一个gulp-less的使用帮助文档README.md；</p>
        <p class="ti15">7.4、为了能正常使用，我们还得本地安装gulp：<strong class="cmd"><code>cnpm install gulp --save-dev</code></strong>；
        </p>
        <p class="ti15">PS：细心的你可能会发现，我们全局安装了gulp，项目也安装了gulp，全局安装gulp是为了执行gulp任务，本地安装gulp则是为了调用gulp插件的功能。</p>
        <h3 id="lesson8">8、新建gulpfile.js文件（重要）</h3>
        <p class="ti15">8.1、说明：gulpfile.js是gulp项目的配置文件，是位于项目根目录的普通js文件（其实将gulpfile.js放入其他文件夹下亦可）。</p>
        <p class="ti15">8.2、它大概是这样一个js文件（更多插件配置请<a href="tag/gulp" target="_blank">查看这里</a>）：</p>
        <div class="code-box">
            <link rel="stylesheet" type="text/css"
                  href="/wp-content/plugins/crayon-syntax-highlighter/fonts/consolas.css">
            <div id="crayon-5726fb0698da7675165787"
                 class="crayon-syntax crayon-theme-raygun crayon-font-consolas crayon-os-pc print-yes notranslate"
                 data-settings=" minimize scroll-mouseover"
                 style=" margin-bottom: 12px; font-size: 14px !important; line-height: 18px !important;">
                <div class="crayon-toolbar" data-settings=" show"
                     style="font-size: 14px !important;height: 21px !important; line-height: 21px !important;"><span
                        class="crayon-title"></span>
                    <div class="crayon-tools"
                         style="font-size: 14px !important;height: 21px !important; line-height: 21px !important;">
                        <div class="crayon-button crayon-nums-button" title="切换是否显示行编号">
                            <div class="crayon-button-icon"></div>
                        </div>
                        <div class="crayon-button crayon-wrap-button" title="切换自动换行">
                            <div class="crayon-button-icon"></div>
                        </div>
                        <div class="crayon-button crayon-expand-button" title="点击展开代码">
                            <div class="crayon-button-icon"></div>
                        </div>
                        <div class="crayon-button crayon-popup-button" title="在新窗口中显示代码">
                            <div class="crayon-button-icon"></div>
                        </div>
                        <span class="crayon-language">JavaScript</span></div>
                </div>
                <div class="crayon-info" style="min-height: 19.6px !important; line-height: 19.6px !important;"></div>
                <div class="crayon-plain-wrap"></div>
                <div class="crayon-main">
                    <table class="crayon-table">
                        <tbody>
                        <tr class="crayon-row">
                            <td class="crayon-nums " data-settings="show">
                                <div class="crayon-nums-content"
                                     style="font-size: 14px !important; line-height: 18px !important;">
                                    <div class="crayon-num" data-line="crayon-5726fb0698da7675165787-1">1</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698da7675165787-2">2
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698da7675165787-3">3</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698da7675165787-4">4
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698da7675165787-5">5</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698da7675165787-6">6
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698da7675165787-7">7</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698da7675165787-8">8
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698da7675165787-9">9</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698da7675165787-10">10
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698da7675165787-11">11</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698da7675165787-12">12
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698da7675165787-13">13</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698da7675165787-14">14
                                    </div>
                                    <div class="crayon-num" data-line="crayon-5726fb0698da7675165787-15">15</div>
                                    <div class="crayon-num crayon-striped-num"
                                         data-line="crayon-5726fb0698da7675165787-16">16
                                    </div>
                                </div>
                            </td>
                            <td class="crayon-code">
                                <div class="crayon-pre"
                                     style="font-size: 14px !important; line-height: 18px !important; -moz-tab-size:4; -o-tab-size:4; -webkit-tab-size:4; tab-size:4;">
                                    <div class="crayon-line" id="crayon-5726fb0698da7675165787-1"><span
                                            class="crayon-c">//导入工具包 require('node_modules里对应模块')</span></div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698da7675165787-2">
                                        <span class="crayon-t">var</span><span class="crayon-h"> </span><span
                                            class="crayon-v">gulp</span><span class="crayon-h"> </span><span
                                            class="crayon-o">=</span><span class="crayon-h"> </span><span
                                            class="crayon-e">require</span><span class="crayon-sy">(</span><span
                                            class="crayon-s">'gulp'</span><span class="crayon-sy">)</span><span
                                            class="crayon-sy">,</span><span class="crayon-h"> </span><span
                                            class="crayon-c">//本地安装gulp所用到的地方</span></div>
                                    <div class="crayon-line" id="crayon-5726fb0698da7675165787-3"><span
                                            class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span
                                            class="crayon-v">less</span><span class="crayon-h"> </span><span
                                            class="crayon-o">=</span><span class="crayon-h"> </span><span
                                            class="crayon-e">require</span><span class="crayon-sy">(</span><span
                                            class="crayon-s">'gulp-less'</span><span class="crayon-sy">)</span><span
                                            class="crayon-sy">;</span></div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698da7675165787-4">
                                        <span class="crayon-h"> </span></div>
                                    <div class="crayon-line" id="crayon-5726fb0698da7675165787-5"><span
                                            class="crayon-c">//定义一个testLess任务（自定义任务名称）</span></div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698da7675165787-6">
                                        <span class="crayon-v">gulp</span><span class="crayon-sy">.</span><span
                                            class="crayon-e">task</span><span class="crayon-sy">(</span><span
                                            class="crayon-s">'testLess'</span><span class="crayon-sy">,</span><span
                                            class="crayon-h"> </span><span class="crayon-t">function</span><span
                                            class="crayon-h"> </span><span class="crayon-sy">(</span><span
                                            class="crayon-sy">)</span><span class="crayon-h"> </span><span
                                            class="crayon-sy">{</span></div>
                                    <div class="crayon-line" id="crayon-5726fb0698da7675165787-7"><span
                                            class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span
                                            class="crayon-v">gulp</span><span class="crayon-sy">.</span><span
                                            class="crayon-e">src</span><span class="crayon-sy">(</span><span
                                            class="crayon-s">'src/less/index.less'</span><span
                                            class="crayon-sy">)</span><span class="crayon-h"> </span><span
                                            class="crayon-c">//该任务针对的文件</span></div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698da7675165787-8">
                                        <span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span
                                            class="crayon-sy">.</span><span class="crayon-e">pipe</span><span
                                            class="crayon-sy">(</span><span class="crayon-e">less</span><span
                                            class="crayon-sy">(</span><span class="crayon-sy">)</span><span
                                            class="crayon-sy">)</span><span class="crayon-h"> </span><span
                                            class="crayon-c">//该任务调用的模块</span></div>
                                    <div class="crayon-line" id="crayon-5726fb0698da7675165787-9"><span
                                            class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span
                                            class="crayon-sy">.</span><span class="crayon-e">pipe</span><span
                                            class="crayon-sy">(</span><span class="crayon-v">gulp</span><span
                                            class="crayon-sy">.</span><span class="crayon-e">dest</span><span
                                            class="crayon-sy">(</span><span class="crayon-s">'src/css'</span><span
                                            class="crayon-sy">)</span><span class="crayon-sy">)</span><span
                                            class="crayon-sy">;</span><span class="crayon-h"> </span><span
                                            class="crayon-c">//将会在src/css下生成index.css</span></div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698da7675165787-10">
                                        <span class="crayon-sy">}</span><span class="crayon-sy">)</span><span
                                            class="crayon-sy">;</span></div>
                                    <div class="crayon-line" id="crayon-5726fb0698da7675165787-11">&nbsp;</div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698da7675165787-12">
                                        <span class="crayon-v">gulp</span><span class="crayon-sy">.</span><span
                                            class="crayon-e">task</span><span class="crayon-sy">(</span><span
                                            class="crayon-s">'default'</span><span class="crayon-sy">,</span><span
                                            class="crayon-sy">[</span><span class="crayon-s">'testLess'</span><span
                                            class="crayon-sy">,</span><span class="crayon-h"> </span><span
                                            class="crayon-s">'elseTask'</span><span class="crayon-sy">]</span><span
                                            class="crayon-sy">)</span><span class="crayon-sy">;</span><span
                                            class="crayon-h"> </span><span class="crayon-c">//定义默认任务</span></div>
                                    <div class="crayon-line" id="crayon-5726fb0698da7675165787-13">&nbsp;</div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698da7675165787-14">
                                        <span class="crayon-c">//gulp.task(name[, deps], fn) 定义任务&nbsp;&nbsp;name：任务名称 deps：依赖任务名称 fn：回调函数</span>
                                    </div>
                                    <div class="crayon-line" id="crayon-5726fb0698da7675165787-15"><span
                                            class="crayon-c">//gulp.src(globs[, options]) 执行任务处理的文件&nbsp;&nbsp;globs：处理的文件路径(字符串或者字符串数组) </span>
                                    </div>
                                    <div class="crayon-line crayon-striped-line" id="crayon-5726fb0698da7675165787-16">
                                        <span class="crayon-c">//gulp.dest(path[, options]) 处理完后文件生成路径</span></div>
                                </div>
                            </td>
                        </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </article>
</div>
