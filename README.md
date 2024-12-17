//
//  ContentView.swift
//  Why not try challange
//
//  Created by Link, Ty - Student on 10/1/24.
//

import SwiftUI

struct ContentView: View {
    
    var activities = ["Archery", "Baseball", "Basketball", "Bowling", "Boxing", "Cricket", "Curling", "Fencing", "Golf", "Hiking", "Lacrosse", "Rugby", "Squash"]
        
    @State var selected = "Baseball"
    
    var colors: [Color] = [.blue, .cyan, .gray, .green, .indigo, .mint, .orange, .pink, .purple, .red]
    
    @State var id = 1
    
    var body: some View {
        VStack {
            Text("Why not try")
                .font(.largeTitle.bold())
            VStack {
                Circle()
                    .fill(colors.randomElement() ?? .blue)
                    .padding()
                    .overlay(
                        Image(systemName: "figure.\(selected.lowercased())")
                            .font(.system(size: 144))
                            .foregroundStyle(.white)
                    )
                Text("\(selected)")
                    .font(.title)
                
            }
            Button("Try again") {
                withAnimation(.easeInOut(duration: 1)) {
                    selected = activities.randomElement() ?? "Archery"
                    id += 1
                    
                }
                
            }
            .buttonStyle(.borderedProminent)
            
            Button(action: {
                
            }, label: {
                Text("Save")
            })
            
            .buttonStyle(.borderedProminent)
           
        }
       
    }
}

#Preview {
    ContentView()
}
