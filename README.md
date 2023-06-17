# member-api-tools 

Member Api Tools  

1. 帳號登入(oauth)
2. 帳號資料查詢(註冊mail、暱稱、頭圖、持有點數總額、付費點數、免費點數、最後登入時間)
3. 查詢交易紀錄(by 遊戲廠商)
4. 扣除點數
5. 取消交易(24小時內)
6. refresh token

## 帳號登入(oauth) 測試方式

```c#
        WWWForm form = new WWWForm();
        form.AddField("grant_type", "password");
        form.AddField("username", LoginUserNameInputField.text);
        form.AddField("password", LoginPasswordInputField.text);
        UnityWebRequest uwr = UnityWebRequest.Post(baseURL + "Account/Login", form);
        yield return uwr.SendWebRequest();

        UnityEngine.Debug.Log(uwr.downloadHandler.text);

        if (uwr.result == UnityWebRequest.Result.ConnectionError)
        {
            
            UnityEngine.Debug.Log("Error: " + uwr.error);
        }
        else
        {
             UnityEngine.Debug.Log(uwr.downloadHandler.text);
        }
```
 

## License

[MIT](https://choosealicense.com/licenses/mit/)
