@startuml

ユーザー -> webサーバー:ログイン
webサーバー -> DBサーバー:ログイン照会
DBサーバー -> DBサーバー:ログイン処理
DBサーバー -> webサーバー:認証結果
webサーバー -> ユーザー:認証結果

activate ユーザー

alt 認証成功
webサーバー ->　ユーザー:ユーザー名を表示

else 認証失敗
webサーバー -> ユーザー:失敗メッセージを表示

end

opt ログイン中

ユーザー -> webサーバー:ログイン
webサーバー -> DBサーバー:ログイン照会
DBサーバー -> DBサーバー:ログイン処理
DBサーバー -> webサーバー:認証結果

end

deactivate ユーザー
@enduml
