# nylon-toast

## Install

```
$ bower install nylon-toast --save
```

## import
```
<link rel="import" href="../bower_components/nylon-toast/nylon-toast.html">
```
## how to use
```
<nylon-toast>
  -- content -- /your components
</nylon-toast>
```

### function 
```
  openToastLoad:function(){ 
    this.fire('toast',{status:'load'}); //คำสั่งสำหรับเปิด toast load
  },
  openToastStatus:function(){
       this.fire('toast',{status:'success',text:'บันทึกสำเร็จ',  // คำสั่งสำหรับเปิด toast success
       callback:function(){
      }
    });
  },
  openToastError:function(){
      this.fire('toast',{status:'connectError',text:'Error code 404 not found', //คำสั่งสำหรับเปิด toast error
      callback:function(){
      }})
  },
  openToastDialog:function(){
      console.log('openDialog');
      this.fire('toast',{  //คำสั่งสำหรับเปิด toast dialog
          status:'dialog',
          text:'ต้องการลบข้อมูลใช่หรือไม่ ?',
          confirmed:this._deleteData, //function ที่ใช้รับค่า ปุ่ม
          el: this, // compontents
          data:'' // ข้อมูลที่ส่งไป เช่น id ที่จะใช้ลบข้อมูล ใน db
      })
  },
  _deleteData:function(result,detail){ //function สำหรับรับค่าปุ่มที่ toast ส่งกลับมา
      console.log('result',result); 
      console.log('detail',detail);
  }
```
