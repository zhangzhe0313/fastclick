# fastclick
fastclick相关笔记

    vue 引入 fastclick.js 解决300ms点击延迟问题，实现加速，但是在chrome56+版本中会出现双击会出现以下问题：
    
        Unable to preventDefault inside passive event listener due to target being treated as passive.
        
     原因是： 新版的chrome对addEventListener事件的默认的行为返回是个对象，不再是bool值
     
     可采用以下方式解决：
     
        addEventListener(type, fn, {passive: false, capture: !!capture})