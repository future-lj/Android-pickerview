**Android-PickerView**

**声明：**该项目只是针对 
作者：xiaosong520
地址：https://github.com/Bigkoo/Android-PickerView 
的进一步修改，目的只为实现项目设计和群内小伙伴的需求，如需查看原项目请自行前往。

实现效果如下：



![效果图](https://github.com/lijin-007/Android-pickerview/blob/master/preview/time_sting.png)


**代码设置：**

  List<String> testH = new ArrayList<>();
        testH.add("上午");
        testH.add("下午");
        TimePickerView pvTime = new TimePickerBuilder(this, new OnTimeSelectListener() {
            @Override
            public void onTimeSelect(Date date, View v) {
                Toast.makeText(MainActivity.this, getTime(date), Toast.LENGTH_SHORT).show();
                Log.i("pvTime", "onTimeSelect");

            }
            @Override
            public void onTimeSelect(String dateStr, View v) {
                Toast.makeText(MainActivity.this, dateStr, Toast.LENGTH_SHORT).show();
    
            }
        })
                .setTimeSelectChangeListener(new OnTimeSelectChangeListener() {
                    @Override
                    public void onTimeSelectChanged(Date date) {
                        Log.i("pvTime", "onTimeSelectChanged");
                    }
                })
                .setLabelHour("")
                .setType(new boolean[]{true, true, true, true, false, false})
                .isDialog(true)
                .setHourLabel(testH)
                .set12Hour(false)
                .build();

onTimeSelect 可在该方法中获取包含string类型的字符串。


**使用：**
1、Add it in your root build.gradle at the end of repositories:

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}

2、Add the dependency
	
		dependencies {
	        implementation 'com.github.lijin-007:Android-pickerview:v1.0.0'
	}
