    ��1��canvas.drawText(String str,x, y, mPaint);
		��һ��������Ҫ���Ƶ��ַ�������
		�ڶ��������ǻ��Ƶ��ַ��Ļ���  ���ֶ����ڻ������ϵ�
		�����������Ǳ� 
		
	��2�������ַ�����ռ�Ŀռ���� 
		Paint.getTextBounds(mCurNum + "", 0, 1, mTextBounds);//�����������ڵľ���  �õ���Ⱥ͸߶�
    ��3��getInterpolation(float input) //����һ��0��1���ֵõ�һ����Ӧ������ ӳ���ֵ��
	��4��������дonMeasure��
		onMeasure(int widthMeasureSpec, int heightMeasureSpec) 
			widthMeasureSpec��heightMeasureSpec����������ֵ���ܻ�� �����mode��size 
			mode��EXACTLY��AT_MOST��UNSPECIFIED���֣�
			EXACTLY��һ������������ȷ��ֵ������MATCH_PARENT
			
			AT_MOST����ʾ�Ӳ���������һ�����ֵ�ڣ�һ��ΪWARP_CONTENT
			UNSPECIFIED����ʾ�Ӳ�����Ҫ���Ͷ�󣬺���ʹ��
			
			
			/**
				��δ��벢û�п���padding
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
				
				
				
				
				
				
			
						
				