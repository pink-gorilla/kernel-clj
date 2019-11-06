(ns klipse-clj.lang.clojure
                        (:require-macros
                          [gadjett.core :refer [dbg]]
                          [cljs.core.async.macros :refer [go go-loop]])
                        (:require
                         klipse-clj.lang.clojure.bundled-namespaces
                          gadjett.core-fn
                          [cljs.tagged-literals :as tags]
                          [goog.dom :as gdom]
                          [clojure.string :refer [blank?]]
                          [klipse-clj.repl :refer [get-completions current-alias-map st create-state-compile current-ns-eval current-ns-compile reset-ns-eval! reset-ns-compile!]]
                          [klipse-clj.lang.clojure.guard :refer [min-max-eval-duration my-emits watchdog]]
                          [klipse-clj.lang.clojure.io :as io]
                          [clojure.pprint :as pprint]
                          [cljs.analyzer :as ana]
                          [klipse-clj.lang.cljs-repl :refer [error->str]] ;; once error->str is in cljs, take it from there
                          [cljs.tools.reader :as r]
                          [cljs.tools.reader.reader-types :as rt]
                          [clojure.string :as s]
                          [cljs.compiler :as compiler]
                         [cljs.core.async :refer [timeout chan close! put! <!]]
                         [cljs.env :as env]
                          [cljs.js :as cljs]))

(enable-console-print!)
(go (<! (create-state-eval))
    (println "init done"))

(go (def b (<! (eval-async-prepl "(map inc [1 2 3)" {}))))

(go (println (<! (eval-async-map "(map inc [1 2 3])" {}))))



