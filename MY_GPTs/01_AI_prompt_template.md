命令文:{
    - def_gpts_main()を実行する。
    - seed値=0
}

maim_functionを定義する。:{
    - def_gpts_main():{
        - description:{
            - AI向け項目説明: このメイン関数自体が実現したいことを記述します。
            - TASK: このメイン関数で達成したい具体的な課題を記述します。
            - objective: このメイン関数全体で達成する具体的な目標を記述します。
        }
        - input:{
            - AI向け項目説明: 想定される、または希望する入力内容を記述します。
            - input_variable(type): 入力される変数の説明とその型を記述します。{
                - default={non}: 指定されない場合のデフォルト値を設定します。
            }
            - variables:{
                - variable_tmp(type): 一時的な計算や保持に使用される変数の説明。{
                    - default={0}: 初期値。
                    - note: 処理中にこの値がどのように変化するかを記述します。
                }
                - const_tmp(type): 計算に使用される定数の説明。{
                    - default={1}: 初期値。
                    - note: この値は変更されません。
                }
            }
        }
        - output:{
            - AI向け項目説明: 希望する出力内容を記述します。関数におけるreturnと同義です。
            - output_variable(type): 出力変数の型と何を出力するかの説明。
        }
        - resource:{
            - AI向け項目説明: 外部データを利用する際の説明を記述します。
            - database: 使用される外部データベースやファイルの説明。{
                - link: 実際にアクセスするリンクを提供します。
            }
        }
        - Processing:{
            - AI向け項目説明: 関数の処理手順を記述します。各functionsを呼び出して制御し、目的を達成します。
            - steps:{
                1. Initialize:{
                    - objective: 初期設定やパラメータの設定を行います。
                    - action: "関連する設定やパラメータの読み込み。"
                }
                2. FunctionCall1:{
                    - objective: 第一の機能を呼び出し、特定のタスクを実行します。
                    - function_call: "def_gpts_function_name1(variable1, variable2, variable3)"
                    - action: "function_name1の結果を取得し、必要な処理を適用します。"
                }
                3. ConditionCheck:{
                    - objective: 状況に応じた条件分岐を評価します。
                    - condition: "if (condition_to_check) then"
                    - true_path: {
                        - action: "条件が真の場合のアクションを実行。"
                    }
                    - false_path: {
                        - action: "条件が偽の場合のアクションを実行。"
                    }
                }
                4. FunctionCall2:{
                    - objective 第二の機能を呼び出し、別のタスクを実行します。
                    - function_call: "def_gpts_function_name2(variable4, variable5)"
                    - action: "function_name2の結果を取得し、続けて処理します。"
                }
                5. RepeatAction:{
                    - objective: 条件を満たすまで特定のアクションを繰り返します。
                    - loop: "while (condition_for_loop) do"
                    - action: "繰り返し実行されるアクションの詳細。"
                }
                6. FinalizeResponse:{
                    - objective: 処理の最終段階で結果を整理し、応答を準備します。
                    - action: "最終的な応答のフォーマットと送信。"
                }
            }
        }
        - exception:{
            - AI向け項目説明: 処理手順において発生する、例外の対処法を記述します。
            - exception_name:{
                - description: 発生可能な例外とそのシナリオを記述します。
                - resolution: 例外に対する解決策を具体的に記述します。
            }
        }
        - restrictions:{
            - AI向け項目説明: 各状況における、制限事項を記述します。
            - 編集不可:{
                - case: このテンプレートを編集するとき
                - description: AI向け項目説明は、AIに対する説明事項のため、記述を編集削除しないでください。
            }
            - restrictions_name:{
                - case: 該当する状況や場合を記述します。
                - description: 制限事項や禁止事項を記述します。
            }
        }
    }
}
個別機能を表すfanctionsを任意数定義する。:{
    - def_gpts_function_name(variable, variable_str, variable_int):{
        - description:{
            - TASK: このプロンプトで達成したい具体的な課題を記述します。
            - objective: この関数によって達成する具体的な目標を記述します。
        }
        - input:{
            - input_variable(type): 入力される変数の説明とその型を記述します。{
                - default={non}: 指定されない場合のデフォルト値を設定します。
            }
            - variables:{
                - variable_tmp(type): 一時的な計算や保持に使用される変数の説明。{
                    - default={0}: 初期値。
                    - note: 処理中にこの値がどのように変化するかを記述します。
                }
                - const_tmp(type): 計算に使用される定数の説明。{
                    - default={1}: 初期値。
                    - note: この値は変更されません。
                }
            }
        }
        - output:{
            - output_variable(type): 出力変数の型と何を出力するかの説明。
        }
        - resource:{
            - database: 使用される外部データベースやファイルの説明。{
                - link: 実際にアクセスするリンクを提供します。
            }
        }
        - Processing:{
            1. IdentifyInputType:{
                - objective: 処理を実行する目的を明確に記述します。
                - Action: 入力データを解析して、データの形式に合わせた処理ルートを選択します。
            }
            2. ExtractRelevantData:{
                - objective: 処理を実行する目的を明確に記述します。
                - Action: テキスト解析ツールを用いて、特定の情報を識別し、抽出します。
            }
            3. PerformDataAnalysis:{
                - objective: 処理を実行する目的を明確に記述します。
                - Action: 分析モデルを適用し、データからインサイトを生成します。
            }
            4. PrepareResponse:{
                - objective: 処理を実行する目的を明確に記述します。
                - Action: 分析結果とユーザーの元の質問を考慮して、適切な応答をフォーマットします。
            }
            5. OutputResponse:{
                - objective: 処理を実行する目的を明確に記述します。
                - Action: 応答をユーザーインターフェースを通じて送信します。
            }
        }
        - exception:{
            - exception_name:{
                - description: 発生可能な例外とそのシナリオを記述します。
                - resolution: 例外に対する解決策を具体的に記述します。
            }
        }
        - restrictions:{
            - restrictions_name:{
                - case: 該当する状況や場合を記述します。
                - description: 制限事項や禁止事項を記述します。
            }
        }
    }
}
note:{
    - 上記はテンプレートです。
    - 関数作成で文字数制限が発生した場合:{
        - functionsのみを別ファイルに記述する。
        - メイン関数のみをプロンプトに記述する。
        - 上記のファイルを、メイン関数から呼び出して読み込む形式にする。
        - 上記一連処理で疑似的に全機能を扱えるようになる。
    }
}