# swiftui_expandable_floating_buttons

```swift
//
//  ContentView.swift
//  FloatingActionButtons
//
//  Created by paige shin on 2023/04/26.
//

import SwiftUI

struct ContentView: View {
    @State var show: Bool = false
    var body: some View {
        ZStack {
            
            
            VStack {
                Spacer()
                HStack {
                    Spacer()
                    ExpandableFAB(show: self.$show)
                }
                .padding(.horizontal, 30)
                
            }
        }
        
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

struct ExpandableFAB: View {
    
    @Binding var show: Bool
    
    var body: some View {
        VStack {
            
            if self.show {
                Button {
                    self.show.toggle()
                } label: {
                    Image(systemName: "tv.fill")
                        .resizable()
                        .scaledToFit()
                        .frame(width: 25, height: 25)
                        .padding(22)
                }
                .background(Color.blue)
                .foregroundColor(.white)
                .clipShape(Circle())
                
                Button {
                    self.show.toggle()
                } label: {
                    Image(systemName: "cart.fill")
                        .resizable()
                        .scaledToFit()
                        .frame(width: 25, height: 25)
                        .padding(22)
                }
                .background(Color.blue)
                .foregroundColor(.white)
                .clipShape(Circle())
            }
            
            Button {
                self.show.toggle()
            } label: {
                Image(systemName: "chevron.up")
                    .resizable()
                    .scaledToFit()
                    .frame(width: 25, height: 25)
                    .padding(22)
            }
            .background(Color.blue)
            .foregroundColor(.white)
            .clipShape(Circle())
            .rotationEffect(.init(degrees: self.show ? 180 : 0))

        } //: VSTACK
        .animation(.default, value: self.show)
    }
    
}

```
