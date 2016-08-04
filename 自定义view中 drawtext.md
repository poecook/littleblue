    《1》canvas.drawText(String str,x, y, mPaint);
		第一个参数是要绘制的字符串内容
		第二个参数是绘制的字符的基线  数字都是在基线以上的
		第三个参数是笔 
		
	《2》计算字符串所占的空间矩形 
		Paint.getTextBounds(mCurNum + "", 0, 1, mTextBounds);//计算文字所在的矩形  得到宽度和高度
    《3》getInterpolation(float input) //输入一个0到1数字得到一个对应的数字 映射插值器
	《4》关于重写onMeasure：
		onMeasure(int widthMeasureSpec, int heightMeasureSpec) 
			widthMeasureSpec和heightMeasureSpec在这两个数值中能获得 具体的mode和size 
			mode有EXACTLY，AT_MOST和UNSPECIFIED三种，
			EXACTLY：一般是设置了明确的值或者是MATCH_PARENT
			
			AT_MOST：表示子布局限制在一个最大值内，一般为WARP_CONTENT
			UNSPECIFIED：表示子布局想要多大就多大，很少使用
			
			
			/**
				这段代码并没有考虑padding
				int widthMode = MeasureSpec.getMode(widthMeasureSpec);  
				int widthSize = MeasureSpec.getSize(widthMeasureSpec);  
				int heightMode = MeasureSpec.getMode(heightMeasureSpec);  
				int heightSize = MeasureSpec.getSize(heightMeasureSpec);  
				int width;  
				int height ;  
				if (widthMode == MeasureSpec.EXACTLY)  
				{  
					width = widthSize;  
				} else  
				{  
					mPaint.setTextSize(mTitleTextSize);  
					mPaint.getTextBounds(mTitle, 0, mTitle.length(), mBounds);  
					float textWidth = mBounds.width();  
					int desired = (int) (getPaddingLeft() + textWidth + getPaddingRight());  
					width = desired;  
				}  
			  
				if (heightMode == MeasureSpec.EXACTLY)  
				{  
					height = heightSize;  
				} else  
				{  
					mPaint.setTextSize(mTitleTextSize);  
					mPaint.getTextBounds(mTitle, 0, mTitle.length(), mBounds);  
					float textHeight = mBounds.height();  
					int desired = (int) (getPaddingTop() + textHeight + getPaddingBottom());  
					height = desired;  
				}  
				  
			  
				setMeasuredDimension(width, height);  
				**/
				
				
				
				
				
				
			
						
				