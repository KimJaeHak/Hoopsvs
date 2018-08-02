> 2018 - 08 - 02 study start

## Hoops Performance

아래의 코드는 **Hoops Visualiize** 에서 Rendering 성능을 빠르게 하기 위한 코드 이다.
이 코드를 분석 해볼 가치가 있음.

```cs
				//view : HbaseView
                
                view.SetSuppressUpdate(true);
                
                view.SetDisplayListType(m_csDisplayList);
                view.SetDisplayListMode(true);

				view.SetOcclusionCullingMode(false, true, 50);
                var oldStaticModel = view.GetModel().GetStaticModel();
            	if (m_bStaticModel != oldStaticModel)
            	{
                	view.GetModel().SetStaticModel(true);
            	}
                view.GetModel().SetLMVModel(true);
                
                var fakeColor = new HPoint(
                m_clrbtnFakeHLR.R / 255.0F,
                m_clrbtnFakeHLR.G / 255.0F,
                m_clrbtnFakeHLR.B / 255.0F
            	);
            	view.SetFakeHLRColor(fakeColor);
                
                view.SetSuppressUpdate(false);
                view.ExhaustiveUpdate(); //view.Update();
```
